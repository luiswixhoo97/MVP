<template>
  <div class="phone-container">
    <div class="phone-frame">
      <div class="notch"></div>

      <div class="screen" ref="screenRef">
        <div class="scroll-content" ref="contentRef" :style="{ transform: `translateY(${scrollPosition}px)` }">
          <!-- Facebook Section -->
          <div class="social-section facebook-section">
            <div class="social-header">
              <div class="social-logo facebook-logo">f</div>
              <span class="social-name">Facebook</span>
            </div>
            <div class="post">
              <div class="post-header">
                <div class="avatar"></div>
                <div class="post-info">
                  <div class="username">María González</div>
                  <div class="time">2h</div>
                </div>
              </div>
              <div class="post-content">
                ¡Qué hermoso día para compartir momentos especiales! 🌟
              </div>
              <div class="post-image"></div>
              <div class="post-actions">
                <div class="action-btn">
                  <span class="like-icon">👍</span>
                  <span class="action-count">{{ facebookLikes }}</span>
                </div>
                <div class="action-btn">
                  <span>💬</span>
                  <span class="action-count">23</span>
                </div>
                <div class="action-btn">
                  <span>↗️</span>
                  <span class="action-count">5</span>
                </div>
              </div>
            </div>
          </div>

          <!-- Instagram Section -->
          <div class="social-section instagram-section">
            <div class="social-header">
              <div class="social-logo instagram-logo">
                <div class="instagram-gradient"></div>
              </div>
              <span class="social-name">Instagram</span>
            </div>
            <div class="instagram-post">
              <div class="post-header">
                <div class="avatar instagram-avatar"></div>
                <div class="post-info">
                  <div class="username">@photographer_pro</div>
                  <div class="location">📍 Barcelona, Spain</div>
                </div>
              </div>
              <div class="instagram-image"></div>
              <div class="instagram-actions">
                <div class="heart-container">
                  <div v-for="heart in hearts" :key="heart.id" class="floating-heart" :style="{ left: heart.x + 'px', animationDelay: heart.delay + 's' }">❤️</div>
                  <span class="heart-icon">❤️</span>
                </div>
                <span class="action-icon">💬</span>
                <span class="action-icon">📤</span>
              </div>
              <div class="likes-count">{{ instagramLikes }} likes</div>
            </div>
          </div>

          <!-- TikTok Section -->
          <div class="social-section tiktok-section">
            <div class="social-header">
              <div class="social-logo tiktok-logo">
                <div class="tiktok-icon"></div>
              </div>
              <span class="social-name">TikTok</span>
            </div>
            <div class="tiktok-video">
              <div class="video-overlay">
                <div class="tiktok-sidebar">
                  <div class="tiktok-action">
                    <div class="tiktok-heart">❤️</div>
                    <span class="tiktok-count">{{ tiktokLikes }}K</span>
                  </div>
                  <div class="tiktok-action">
                    <div class="tiktok-comment">💬</div>
                    <span class="tiktok-count">1.2K</span>
                  </div>
                  <div class="tiktok-action">
                    <div class="tiktok-share">↗️</div>
                    <span class="tiktok-count">856</span>
                  </div>
                </div>
                <div class="tiktok-info">
                  <div class="tiktok-username">@dancemoves</div>
                  <div class="tiktok-description">New dance trend! 💃 #viral #dance</div>
                </div>
              </div>
            </div>
          </div>

          <!-- YouTube Section -->
          <div class="social-section youtube-section">
            <div class="social-header">
              <div class="social-logo youtube-logo">▶️</div>
              <span class="social-name">YouTube</span>
            </div>
            <div class="youtube-video">
              <div class="video-thumbnail">
                <div class="play-button">▶️</div>
              </div>
              <div class="video-info">
                <div class="video-title">Cómo crear animaciones increíbles con CSS</div>
                <div class="video-stats">
                  <span>{{ youtubeViews }}K views</span>
                  <span>•</span>
                  <span>3 days ago</span>
                </div>
                <div class="video-actions">
                  <div class="youtube-action">
                    <span>👍</span>
                    <span>{{ youtubeLikes }}K</span>
                  </div>
                  <div class="youtube-action">
                    <span>👎</span>
                    <span>12</span>
                  </div>
                  <div class="youtube-action">
                    <span>↗️</span>
                    <span>Share</span>
                  </div>
                </div>
              </div>
            </div>
          </div>

          <!-- Google Ads Section -->
          <div class="social-section ads-section">
            <div class="social-header">
              <div class="social-logo google-logo">G</div>
              <span class="social-name">Google Ads</span>
            </div>
            <div class="ad-container">
              <div class="ad-label">Sponsored</div>
              <div class="ad-content">
                <div class="ad-image"></div>
                <div class="ad-text">
                  <div class="ad-title">Aprende Desarrollo Web</div>
                  <div class="ad-description">Cursos online certificados. ¡Empieza hoy!</div>
                  <div class="ad-url">www.webdev-courses.com</div>
                </div>
              </div>
              <div class="ad-cta">Más información</div>
            </div>
          </div>

        </div>
      </div>

      <div class="home-button"></div>
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const scrollPosition = ref(0)
const maxScroll = ref(0)
const screenRef = ref(null)
const contentRef = ref(null)
const facebookLikes = ref(127)
const instagramLikes = ref(1543)
const tiktokLikes = ref(89)
const youtubeViews = ref(234)
const youtubeLikes = ref(18)
const hearts = ref([])

let scrollInterval
let heartInterval
let likesInterval

const computeMaxScroll = () => {
  if (!screenRef.value || !contentRef.value) return
  const screenH = screenRef.value.clientHeight || 0
  const contentH = contentRef.value.scrollHeight || 0
  maxScroll.value = Math.max(0, contentH - screenH)
}

onMounted(() => {
  computeMaxScroll()
  window.addEventListener('resize', computeMaxScroll)

  scrollInterval = setInterval(() => {
    scrollPosition.value -= 1
    if (Math.abs(scrollPosition.value) >= maxScroll.value) {
      // Reiniciar justo cuando termina el último bloque (Google Ads)
      scrollPosition.value = 0
    }
  }, 50)

  heartInterval = setInterval(() => {
    if (hearts.value.length < 5) {
      hearts.value.push({ id: Date.now(), x: Math.random() * 30, delay: Math.random() * 2 })
    }
    if (hearts.value.length > 8) {
      hearts.value = hearts.value.slice(-5)
    }
  }, 1500)

  likesInterval = setInterval(() => {
    facebookLikes.value += Math.floor(Math.random() * 3)
    instagramLikes.value += Math.floor(Math.random() * 5)
    tiktokLikes.value += Math.floor(Math.random() * 2)
    youtubeViews.value += Math.floor(Math.random() * 4)
    youtubeLikes.value += Math.floor(Math.random() * 2)
  }, 3000)
})

onUnmounted(() => {
  if (scrollInterval) clearInterval(scrollInterval)
  if (heartInterval) clearInterval(heartInterval)
  if (likesInterval) clearInterval(likesInterval)
  window.removeEventListener('resize', computeMaxScroll)
})
</script>

<style scoped>
.phone-container { position: relative; }
.phone-frame {
  width: 300px; height: 560px; background: linear-gradient(145deg, #2a2a2a, #1a1a1a);
  border-radius: 35px; padding: 20px;
  box-shadow: 0 0 50px rgba(0,0,0,.5), inset 0 2px 10px rgba(255,255,255,.1);
  position: relative;
}
.notch { position: absolute; top: 8px; left: 50%; transform: translateX(-50%);
  width: 120px; height: 25px; background: #000; border-radius: 15px; z-index: 10; }
.screen { width: 100%; height: 100%; background: #000; border-radius: 25px; overflow: hidden; position: relative; }
.scroll-content { width: 100%; transition: transform .1s linear; }
.social-section { height: 480px; padding: 20px; border-bottom: 1px solid #333; }
.facebook-section { background: linear-gradient(135deg, #1877f2, #42a5f5); }
.social-header { display: flex; align-items: center; margin-bottom: 20px; }
.social-logo { width: 40px; height: 40px; border-radius: 50%; display:flex; align-items:center; justify-content:center; font-weight: bold; margin-right: 10px; }
.facebook-logo { background: #fff; color: #1877f2; font-size: 24px; }
.social-name { color:#fff; font-weight:bold; font-size:18px; }
.post { background: rgba(255,255,255,.95); border-radius: 15px; padding: 15px; color:#333; }
.post-header { display:flex; align-items:center; margin-bottom:10px; }
.avatar { width:40px; height:40px; border-radius:50%; background: linear-gradient(45deg,#ff6b6b,#4ecdc4); margin-right:10px; }
.username { font-weight:bold; font-size:14px; }
.time { color:#666; font-size:12px; }
.post-content { margin:10px 0; line-height:1.4; }
.post-image { height:150px; background: linear-gradient(45deg,#ff9a9e,#fecfef); border-radius:10px; margin:10px 0; }
.post-actions { display:flex; justify-content:space-around; padding-top:10px; border-top:1px solid #eee; }
.action-btn { display:flex; align-items:center; gap:5px; padding:5px 10px; border-radius:20px; background: rgba(24,119,242,.1); transition: all .3s ease; }
.action-count { font-size:12px; font-weight:bold; color:#1877f2; }
.instagram-section { background: linear-gradient(135deg,#833ab4,#fd1d1d,#fcb045); }
.instagram-logo { background:#fff; position:relative; overflow:hidden; }
.instagram-gradient { position:absolute; inset:2px; border-radius:50%; background: linear-gradient(45deg,#833ab4,#fd1d1d,#fcb045); }
.instagram-post { background: rgba(255,255,255,.95); border-radius:15px; padding:15px; color:#333; }
.instagram-avatar { border:2px solid #fd1d1d; }
.location { color:#666; font-size:12px; }
.instagram-image { height:200px; background: linear-gradient(45deg,#667eea,#764ba2); border-radius:10px; margin:10px 0; }
.instagram-actions { display:flex; align-items:center; gap:15px; margin:10px 0; position:relative; }
.heart-container { position:relative; }
.floating-heart { position:absolute; animation: floatHeart 3s ease-out forwards; pointer-events:none; font-size:12px; }
@keyframes floatHeart { 0%{opacity:1; transform: translateY(0) scale(1);} 100%{opacity:0; transform: translateY(-50px) scale(1.5);} }
.action-icon { font-size:20px; cursor:pointer; }
.likes-count { font-weight:bold; font-size:14px; }
.tiktok-section { background: linear-gradient(135deg,#000,#ff0050); }
.tiktok-logo { background:#000; color:#ff0050; }
.tiktok-icon { width:20px; height:20px; background: linear-gradient(45deg,#ff0050,#00f2ea); border-radius:3px; }
.tiktok-video { height:380px; background: linear-gradient(45deg,#667eea,#764ba2); border-radius:15px; position:relative; overflow:hidden; }
.video-overlay { position:absolute; inset:0; background: rgba(0,0,0,.3); display:flex; justify-content:space-between; align-items:flex-end; padding:20px; }
.tiktok-sidebar { display:flex; flex-direction:column; gap:20px; align-items:center; }
.tiktok-action { display:flex; flex-direction:column; align-items:center; gap:5px; }
.tiktok-heart,.tiktok-comment,.tiktok-share { width:40px; height:40px; border-radius:50%; background: rgba(255,255,255,.2); display:flex; align-items:center; justify-content:center; font-size:18px; animation: pulse 2s infinite; }
.tiktok-count { color:#fff; font-size:12px; font-weight:bold; }
.tiktok-info { flex:1; color:#fff; }
.tiktok-username { font-weight:bold; margin-bottom:5px; }
.tiktok-description { font-size:14px; line-height:1.3; }
.youtube-section { background: linear-gradient(135deg,#ff0000,#cc0000); }
.youtube-logo { background:#fff; color:#ff0000; font-size:20px; }
.youtube-video { background: rgba(255,255,255,.95); border-radius:15px; padding:15px; color:#333; }
.video-thumbnail { height:180px; background: linear-gradient(45deg,#667eea,#764ba2); border-radius:10px; display:flex; align-items:center; justify-content:center; margin-bottom:10px; position:relative; }
.play-button { width:60px; height:60px; border-radius:50%; background: rgba(255,0,0,.9); color:#fff; display:flex; align-items:center; justify-content:center; font-size:24px; animation: pulse 2s infinite; }
.video-title { font-weight:bold; margin-bottom:5px; line-height:1.3; }
.video-stats { color:#666; font-size:12px; margin-bottom:10px; }
.video-actions { display:flex; gap:20px; }
.youtube-action { display:flex; align-items:center; gap:5px; font-size:12px; }
.ads-section { background: linear-gradient(135deg,#4285f4,#34a853); }
.google-logo { background:#fff; color:#4285f4; font-weight:bold; font-size:20px; }
.ad-container { background: rgba(255,255,255,.95); border-radius:15px; padding:15px; color:#333; }
.ad-label { background:#4285f4; color:#fff; padding:2px 8px; border-radius:4px; font-size:10px; display:inline-block; margin-bottom:10px; }
.ad-content { display:flex; gap:15px; margin-bottom:15px; }
.ad-image { width:80px; height:80px; background: linear-gradient(45deg,#4285f4,#34a853); border-radius:8px; flex-shrink:0; }
.ad-text { flex:1; }
.ad-title { font-weight:bold; margin-bottom:5px; color:#1a73e8; }
.ad-description { font-size:14px; margin-bottom:5px; line-height:1.3; }
.ad-url { color:#34a853; font-size:12px; }
.ad-cta { background:#4285f4; color:#fff; padding:8px 16px; border-radius:20px; text-align:center; font-weight:bold; cursor:pointer; transition: all .3s ease; }
.ad-cta:hover { background:#3367d6; transform: translateY(-1px); }
.home-button { position:absolute; bottom:5px; left:50%; transform: translateX(-50%); width:50px; height:4px; background:#666; border-radius:2px; }
@keyframes pulse { 0%,100%{ transform: scale(1);} 50%{ transform: scale(1.05);} }
</style>



