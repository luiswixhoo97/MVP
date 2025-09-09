<template>
    <div class="min-h-screen bg-white py-24">
      <div class="container mx-auto px-6">
         
        <div class="text-center mb-12 sm:mb-16 px-2">
          <h1 class="text-4xl sm:text-5xl lg:text-6xl font-bold mb-4">
            <span class="bg-gradient-to-r from-purple-600 via-pink-600 to-orange-500 bg-clip-text text-transparent">Nuestros Servicios</span>
          </h1>
        </div>
  
          
        <div class="space-y-12">
           
          <!-- Campañas Ads Meta y Google (primero) -->
          <div class="glass p-6 sm:p-8 lg:p-12 hover:shadow-2xl transition-all duration-500">
            <div class="grid lg:grid-cols-2 gap-6 sm:gap-8 items-center">
              <div class="order-2 lg:order-2">
                <h3 class="text-2xl sm:text-3xl lg:text-4xl font-bold text-gray-900 mb-3 sm:mb-4">Campañas Ads Meta y Google</h3>
                <p class="text-gray-700 mb-5 sm:mb-6 leading-relaxed">Campañas en Meta (Facebook, Instagram) y Google Ads con enfoque 100% orientado a resultados: alcance, leads y ventas.</p>
                <ul class="space-y-3 mb-8">
                  <li class="flex items-center text-gray-700">
                    <span class="text-orange-500 mr-3 text-lg">→</span>
                    Segmentación precisa y creatividades A/B
                  </li>
                  <li class="flex items-center text-gray-700">
                    <span class="text-orange-500 mr-3 text-lg">→</span>
                    Optimización y medición continua
                  </li>
                  <li class="flex items-center text-gray-700">
                    <span class="text-orange-500 mr-3 text-lg">→</span>
                    Generación de leads y ventas
                  </li>
                </ul>
                <a :href="whatsAppUrl('Campañas Ads Meta y Google')" target="_blank" class="bg-gradient-to-r from-orange-500 to-red-500 text-white mx-auto lg:mx-0 w-fit px-8 py-4 rounded-xl font-semibold hover:from-orange-600 hover:to-red-600 transform hover:scale-105 transition-all duration-300 shadow-lg">
                  Contactanos
                </a>
              </div>
              <div class="w-full h-72 sm:h-80 rounded-2xl p-4 md:p-6 relative shadow-xl order-1 lg:order-2 bg-white ads-sim">
                <div class="ads-body">
                  <div class="channels">
                    <div v-for="ch in channels" :key="ch.name" class="channel-row">
                      <div class="dot" :style="{ background: ch.color }"></div>
                      <span class="ch-name">{{ ch.name }}</span>
                      <div class="bar"><div class="fill" :style="{ width: ch.share + '%', background: ch.color }"></div></div>
                      <span class="val">{{ ch.share }}%</span>
                    </div>
                  </div>
                  <div class="kpis">
                    <div class="kpi"><span>Impresiones</span><span class="val">{{ adImpressions.toLocaleString() }}</span></div>
                    <div class="kpi"><span>Clics</span><span class="val">{{ adClicks.toLocaleString() }}</span></div>
                    <div class="kpi"><span>Conversiones</span><span class="val">{{ adConversions.toLocaleString() }}</span></div>
                    <div class="kpi">
                      <span>CTR</span><span class="val">{{ ctr.toFixed(1) }}%</span>
                      <div class="bar"><div class="fill" :style="{ width: Math.min(100, (ctr)) + '%' }"></div></div>
                    </div>
                    <div class="kpi"><span>CPA</span><span class="val">${{ cpa.toFixed(2) }}</span></div>
                    <div class="kpi">
                      <span>Presupuesto</span>
                      <div class="bar budget"><div class="fill" :style="{ width: budgetPct + '%' }"></div></div>
                      <span class="val">{{ spend.toFixed(1) }}k / {{ budgetTotal }}k</span>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
          
          <!-- Representación de creadores -->
          <div class="glass p-6 sm:p-8 lg:p-12 hover:shadow-2xl transition-all duration-500">
            <div class="grid lg:grid-cols-2 gap-6 sm:gap-8 items-center">
              <div class="order-2 lg:order-2">
                <h3 class="text-2xl sm:text-3xl lg:text-4xl font-bold text-gray-900 mb-3 sm:mb-4">Representación de Creadores</h3>
                <p class="text-gray-700 mb-6 leading-relaxed max-w-[70ch]">Representamos talento y creadores de contenido para campañas con objetivos claros. Velamos por acuerdos justos, entregables de calidad y resultados medibles.</p>
                <ul class="space-y-3 mb-8">
                  <li class="flex items-center text-gray-700"><span class="text-purple-500 mr-3 text-lg">→</span>Selección y casting según audiencia y briefing</li>
                  <li class="flex items-center text-gray-700"><span class="text-purple-500 mr-3 text-lg">→</span>Negociación, contratos y gestión de derechos</li>
                  <li class="flex items-center text-gray-700"><span class="text-purple-500 mr-3 text-lg">→</span>Coordinación de entregables y reporting</li>
                </ul>
                <a :href="whatsAppUrl('Representación de Creadores')" target="_blank" class="bg-gradient-to-r from-purple-500 to-pink-500 text-white mx-auto lg:mx-0 w-fit px-8 py-4 rounded-xl font-semibold hover:from-purple-600 hover:to-pink-600 transform hover:scale-105 transition-all duration-300 shadow-lg">Contactanos</a>
              </div>
              <div class="w-full h-72 sm:h-80 bg-gradient-to-br from-purple-50 to-pink-50 rounded-2xl p-3 md:p-4 shadow-xl order-1 lg:order-1 overflow-hidden relative">
                <div class="creator-carousel" @mouseenter="isCarouselHovered = true" @mouseleave="isCarouselHovered = false">
                  <div class="creator-track" :style="{ '--offsetX': `${-carouselIndex * (cardWidthPx + gapPx)}px` }">
                    <div v-for="card in creatorsCarousel" :key="card.name" class="creator-card">
                      <div class="creator-top">
                        <div class="avatar-grad" :style="{ background: `linear-gradient(135deg, ${card.colors[0]}, ${card.colors[1]})` }"></div>
                        <span class="platform-pill">{{ card.platform }}</span>
                      </div>
                      <div class="creator-name">{{ card.name }}</div>
                      <div class="creator-stats">
                        <span>{{ card.followers }}K</span>
                        <span>Eng {{ card.engagement }}%</span>
                      </div>
                      <div class="creator-tags">
                        <span class="tag">Moda</span>
                        <span class="tag">Lifestyle</span>
                      </div>
                      <div class="mini-metric">
                        <div class="mini-label">Último post</div>
                        <div class="bar"><div class="fill" style="width: 72%"></div></div>
                      </div>
                    </div>
                  </div>
                </div>
                <div class="edge-mask left"></div>
                <div class="edge-mask right"></div>
              </div>
            </div>
          </div>

          <!-- Producción de contenido audiovisual -->
          <div class="glass p-6 sm:p-8 lg:p-12 hover:shadow-2xl transition-all duration-500">
            <div class="grid lg:grid-cols-2 gap-6 sm:gap-8 items-center">
              <div class="order-2 lg:order-1">
                <h3 class="text-2xl sm:text-3xl lg:text-4xl font-bold text-gray-900 mb-3 sm:mb-4">Producción de Contenido Audiovisual</h3>
                <p class="text-gray-700 mb-6 leading-relaxed max-w-[70ch]">Concepto, guion, grabación, edición y postproducción. Piezas diseñadas para captar atención y convertir, desde corporativos hasta contenido social.</p>
                <ul class="space-y-3 mb-8">
                  <li class="flex items-center text-gray-700"><span class="text-blue-500 mr-3 text-lg">→</span>Videos corporativos y comerciales</li>
                  <li class="flex items-center text-gray-700"><span class="text-blue-500 mr-3 text-lg">→</span>Contenido dinámico para redes</li>
                  <li class="flex items-center text-gray-700"><span class="text-blue-500 mr-3 text-lg">→</span>Estándares de excelencia visual</li>
                </ul>
                <a :href="whatsAppUrl('Producción de Contenido Audiovisual')" target="_blank" class="bg-gradient-to-r from-blue-500 to-cyan-500 text-white mx-auto lg:mx-0 w-fit px-8 py-4 rounded-xl font-semibold hover:from-blue-600 hover:to-cyan-600 transform hover:scale-105 transition-all duration-300 shadow-lg">Contactanos</a>
              </div>
              <div class="w-full h-72 sm:h-80 rounded-2xl p-0 relative shadow-xl overflow-hidden bg-white order-1 lg:order-2 yt-sim">
                <div class="yt-screen">
                  <div class="yt-overlay"></div>
                  <div class="yt-play">
                    <div class="triangle"></div>
                  </div>
                  <div class="yt-pulse"></div>
                </div>
                <div class="yt-controls">
                  <div class="progress">
                    <div class="progress-fill" :style="{ width: ytProgress + '%' }"></div>
                  </div>
                  <div class="meta">
                    <div class="left">
                      <span class="dot live"></span>
                      <span class="label">YouTube Preview</span>
                    </div>
                    <div class="right">
                      <span class="pill subscribe">SUBSCRIBIRSE</span>
                      <span class="stat">👍 1.2K</span>
                      <span class="stat">👁️ 24K</span>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>

          <!-- Community Management -->
          <div class="glass p-6 sm:p-8 lg:p-12 hover:shadow-2xl transition-all duration-500">
            <div class="grid lg:grid-cols-2 gap-6 sm:gap-8 items-center">
              <!-- Visual left: chat/feed simulation -->
              <div class="w-full h-72 sm:h-80 bg-gradient-to-br from-purple-100 to-pink-100 rounded-2xl p-4 relative shadow-xl order-1 lg:order-1 overflow-hidden">
                <div class="cm-sim">
                  <div class="cm-header">
                    <div class="cm-avatar"></div>
                    <span class="cm-title">Community</span>
                    <span v-if="cmUnread > 0" class="cm-badge">{{ cmUnread }}</span>
                  </div>
                  <div class="cm-feed" ref="cmFeedRef">
                    <div v-for="m in cmMessages" :key="m.id" class="cm-bubble" :class="m.side">
                      <div class="cm-text">{{ m.text }}</div>
                      <div class="cm-meta">{{ m.time }} · ❤️ {{ m.reacts }}</div>
                    </div>
                    <div v-if="cmTyping" class="cm-bubble left typing"><span></span><span></span><span></span></div>
                  </div>
                  <div class="cm-input">
                    <div class="cm-pill">Programar post · 10:00</div>
                    <div class="cm-pill">Responder</div>
                  </div>
                </div>
              </div>
              <!-- Text right -->
              <div class="order-2 lg:order-2">
                <h3 class="text-4xl font-bold text-gray-900 mb-4">Community Management</h3>
                <p class="text-gray-700 mb-6 leading-relaxed max-w-[70ch]">Gestión de redes sociales: calendarios editoriales, atención a mensajes y construcción de comunidades coherentes con tu identidad.</p>
                <ul class="space-y-3 mb-8">
                  <li class="flex items-center text-gray-700"><span class="text-purple-500 mr-3 text-lg">→</span>Planificación y producción de contenido</li>
                  <li class="flex items-center text-gray-700"><span class="text-purple-500 mr-3 text-lg">→</span>Monitoreo y respuesta a la comunidad</li>
                  <li class="flex items-center text-gray-700"><span class="text-purple-500 mr-3 text-lg">→</span>Consistencia de marca y crecimiento orgánico</li>
                </ul>
                <a :href="whatsAppUrl('Community Management')" target="_blank" class="bg-gradient-to-r from-purple-500 to-pink-500 text-white mx-auto lg:mx-0 w-fit px-8 py-4 rounded-xl font-semibold hover:from-purple-600 hover:to-pink-600 transform hover:scale-105 transition-all duration-300 shadow-lg">Contactanos</a>
              </div>
            </div>
          </div>
          <!-- Contratación de Medios ON & OFF moved later -->

          <!-- Contratación de Medios ON & OFF (colocado al final para alternar entradas) -->
          <div class="glass p-6 sm:p-8 lg:p-12 hover:shadow-2xl transition-all duration-500">
            <div class="grid lg:grid-cols-2 gap-6 sm:gap-8 items-center">
              <div class="order-2 lg:order-1">
                <h3 class="text-2xl sm:text-3xl lg:text-4xl font-bold text-gray-900 mb-3 sm:mb-4">Contratación de medios publicitarios ON & OFF</h3>
                <p class="text-gray-700 mb-6 leading-relaxed max-w-[70ch]">Acceso a una red estratégica de medios digitales y tradicionales con cobertura a nivel nacional para visibilidad y posicionamiento.</p>
                <ul class="space-y-3 mb-8">
                  <li class="flex items-center text-gray-700">
                    <span class="text-pink-500 mr-3 text-lg">→</span>
                    Medios OFF: espectaculares, muros, centros comerciales, pantallas digitales, camiones urbanos
                  </li>
                  <li class="flex items-center text-gray-700">
                    <span class="text-pink-500 mr-3 text-lg">→</span>
                    Medios ON: RRSS, contratación y gestión de influencers y creadores UGC
                  </li>
                  <li class="flex items-center text-gray-700">
                    <span class="text-pink-500 mr-3 text-lg">→</span>
                    Planeación, negociación, ejecución y reportes con evidencia y métricas
                  </li>
                </ul>
                <a :href="whatsAppUrl('Contratación de Medios ON & OFF')" target="_blank" class="bg-gradient-to-r from-pink-500 to-orange-500 text-white mx-auto lg:mx-0 w-fit px-8 py-4 rounded-xl font-semibold hover:from-pink-600 hover:to-orange-600 transform hover:scale-105 transition-all duration-300 shadow-lg">
                  Contactanos
                </a>
              </div>
              <div class="w-full h-72 sm:h-80 bg-gradient-to-br from-pink-50 to-orange-50 rounded-2xl p-0 relative shadow-xl order-1 lg:order-2 media-sim">
                <div class="map">
                  <div v-for="site in mediaSites" :key="site.id" class="site" :class="{ active: site.active }" :style="{ left: site.x + '%', top: site.y + '%' }">
                    <div class="panel"></div>
                    <div class="pin"></div>
                  </div>
                </div>
                <div class="legend">
                  <div class="item"><span class="led on"></span><span>ON</span></div>
                  <div class="item"><span class="led off"></span><span>OFF</span></div>
                </div>
                <div class="booking">
                  <div class="label">Cobertura</div>
                  <div class="bar"><div class="fill" :style="{ width: mediaCoverage + '%' }"></div></div>
                </div>
              </div>
            </div>
          </div>
           
          <div class="glass p-6 sm:p-8 lg:p-12 hover:shadow-2xl transition-all duration-500">
            <div class="grid lg:grid-cols-2 gap-6 sm:gap-8 items-center">
              <div class="order-2 lg:order-2">
                <h3 class="text-2xl sm:text-3xl lg:text-4xl font-bold text-gray-900 mb-3 sm:mb-4">Desarrollo Web</h3>
                <p class="text-gray-700 mb-6 leading-relaxed max-w-[70ch]">Creamos sitios web modernos, funcionales y diseñados estratégicamente para convertir visitantes en clientes, con foco en UX/UI, velocidad y SEO.</p>
                <ul class="space-y-3 mb-8">
                  <li class="flex items-center text-gray-700">
                    <span class="text-pink-500 mr-3 text-lg">→</span>
                    UX/UI enfocada en conversión
                  </li>
                  <li class="flex items-center text-gray-700">
                    <span class="text-pink-500 mr-3 text-lg">→</span>
                    Formularios, chatbots y analítica
                  </li>
                  <li class="flex items-center text-gray-700">
                    <span class="text-pink-500 mr-3 text-lg">→</span>
                    SEO técnico y performance
                  </li>
                </ul>
                <a :href="whatsAppUrl('Desarrollo Web')" target="_blank" class="bg-gradient-to-r from-pink-500 to-orange-500 text-white mx-auto lg:mx-0 w-fit px-8 py-4 rounded-xl font-semibold hover:from-pink-600 hover:to-orange-600 transform hover:scale-105 transition-all duration-300 shadow-lg">
                  Contactanos
                </a>
              </div>
              <div class="w-full h-72 sm:h-80 bg-white rounded-2xl p-6 relative overflow-hidden shadow-xl order-1 lg:order-1 lg:order-first">
                <div class="bg-white rounded-xl w-full h-full overflow-hidden relative page-sim">
                  <div class="nav-sim" :class="{ 'is-visible': buildStep >= 1 }">
                    <div class="brand-sim" :class="{ 'is-visible': buildStep >= 2 }"></div>
                    <div class="nav-links">
                      <span v-for="i in 3" :key="'nav'+i" class="nav-pill" :class="{ 'is-visible': buildStep >= 2 }"></span>
                    </div>
                  </div>
                  <div class="hero-sim" :class="{ 'is-visible': buildStep >= 3 }">
                    <div class="hero-title-sim" :class="{ 'is-visible': buildStep >= 4 }"></div>
                    <div class="hero-sub-sim" :class="{ 'is-visible': buildStep >= 4 }"></div>
                    <div class="hero-cta-row">
                      <div class="cta-sim primary" :class="{ 'is-visible': buildStep >= 5 }"></div>
                      <div class="cta-sim ghost" :class="{ 'is-visible': buildStep >= 5 }"></div>
                    </div>
                  </div>
                  <div class="cards-row" :class="{ 'is-visible': buildStep >= 6 }">
                    <div v-for="i in 3" :key="'card'+i" class="card-sim" :class="{ 'is-visible': buildStep >= 7 }">
                      <div class="card-media"></div>
                      <div class="card-title"></div>
                      <div class="card-text"></div>
                    </div>
                  </div>
                  <div class="footer-sim" :class="{ 'is-visible': buildStep >= 8 }">
                    <div class="footer-block"></div>
                    <div class="footer-block"></div>
                    <div class="footer-block"></div>
                  </div>
                </div>
                <div class="absolute bottom-4 right-4 w-3 h-3 bg-green-400 rounded-full animate-pulse"></div>
              </div>
            </div>
          </div>
  
            
          <div class="glass p-6 sm:p-8 lg:p-12 hover:shadow-2xl transition-all duration-500">
            <div class="grid lg:grid-cols-2 gap-6 sm:gap-8 items-center">
              <div class="order-2 lg:order-1">
                <h3 class="text-2xl sm:text-3xl lg:text-4xl font-bold text-gray-900 mb-3 sm:mb-4">Influencer Marketing y UGC</h3>
                <p class="text-gray-700 mb-6 leading-relaxed max-w-[70ch]">Conectamos marcas con creadores adecuados para contenido auténtico y relevante. Selección, negociación, producción y medición integral.</p>
                <ul class="space-y-3 mb-8">
                  <li class="flex items-center text-gray-700">
                    <span class="text-purple-500 mr-3 text-lg">→</span>
                    Estrategias con influencers y microinfluencers
                  </li>
                  <li class="flex items-center text-gray-700">
                    <span class="text-purple-500 mr-3 text-lg">→</span>
                    Gestión de UGC y representación de creadores
                  </li>
                  <li class="flex items-center text-gray-700">
                    <span class="text-purple-500 mr-3 text-lg">→</span>
                    Medición de resultados y optimización
                  </li>
                </ul>
                <a :href="whatsAppUrl('Influencer Marketing y UGC')" target="_blank" class="bg-gradient-to-r from-purple-500 to-pink-500 text-white mx-auto lg:mx-0 w-fit px-8 py-4 rounded-xl font-semibold hover:from-purple-600 hover:to-pink-600 transform hover:scale-105 transition-all duration-300 shadow-lg">
                  Contactanos
                </a>
              </div>
              <div class="w-full h-72 sm:h-80 rounded-2xl p-3 relative overflow-hidden shadow-xl order-1 lg:order-2 im-metrics-frame">
                <div class="im-card">
                  <div class="im-header">
                    <span class="title">Social Dashboard</span>
                    <span class="dot green"></span>
            </div>
                  <div class="im-top">
                    <div class="stat-card">
                      <div class="label">Seguidores</div>
                      <div class="value">{{ imFollowers.toLocaleString() }}</div>
                    </div>
                    <div class="stat-card">
                      <div class="label">Engagement</div>
                      <div class="value">{{ imEngagement.toFixed(1) }}%</div>
                    </div>
                      </div>
                  <div class="reach-card">
                    <div class="label">Alcance Semanal</div>
                    <div class="value">{{ imReach.toLocaleString() }}</div>
                    <div class="bar"><div class="fill" :style="{ width: Math.min(100, Math.round((imReach/imGoal)*100)) + '%' }"></div></div>
                    </div>
                  <div class="im-footer">
                    <div class="delta">⚡ {{ imDelta }} vs semana anterior</div>
                    <div class="goal">🎯 Meta: {{ imGoal/1000 }}K</div>
                  </div>
                </div>
              </div>
            </div>
          </div>
  
           
          
  
           
          <div class="glass p-10 lg:p-12 hover:shadow-2xl transition-all duration-500">
            <div class="grid lg:grid-cols-2 gap-8 items-center">
              <div class="w-full h-80 bg-gradient-to-br from-purple-100 to-pink-100 rounded-2xl p-6 relative shadow-xl order-1 lg:order-1">
                <div class="text-center">
                  <h4 class="text-xl font-bold text-gray-800 mb-6">Paleta de Colores</h4>
                  <div class="grid grid-cols-4 gap-4 mb-6">
                    <div v-for="(color, index) in brandColors" :key="index" 
                         class="w-16 h-16 rounded-xl transform transition-all duration-500 hover:scale-110 cursor-pointer shadow-lg"
                         :style="{ backgroundColor: color, transform: activeBrandColor === index ? 'scale(1.2)' : 'scale(1)' }"
                         @click="activeBrandColor = index">
                    </div>
                  </div>
                  <div class="bg-white rounded-lg p-3 shadow-md">
                    <div class="text-sm font-semibold text-gray-700">Color Seleccionado</div>
                    <div class="text-xs text-gray-500">{{ brandColors[activeBrandColor] }}</div>
                  </div>
                </div>
              </div>
              <div class="order-2 lg:order-2">
                <h3 class="text-4xl font-bold text-gray-900 mb-4">Branding y diseño gráfico</h3>
                <p class="text-gray-700 mb-6 leading-relaxed max-w-[70ch]">Definimos identidad visual y conceptual que transmite confianza, profesionalismo y diferenciación.</p>
                <ul class="space-y-3 mb-8">
                  <li class="flex items-center text-gray-700">
                    <span class="text-purple-500 mr-3 text-lg">→</span>
                    Logotipo e identidad visual
                  </li>
                  <li class="flex items-center text-gray-700">
                    <span class="text-purple-500 mr-3 text-lg">→</span>
                    Manual de marca y lineamientos
                  </li>
                  <li class="flex items-center text-gray-700">
                    <span class="text-purple-500 mr-3 text-lg">→</span>
                    Piezas gráficas para campañas y redes
                  </li>
                </ul>
                <a :href="whatsAppUrl('Branding y diseño gráfico')" target="_blank" class="bg-gradient-to-r from-purple-500 to-indigo-500 text-white mx-auto lg:mx-0 w-fit px-8 py-4 rounded-xl font-semibold hover:from-purple-600 hover:to-indigo-600 transform hover:scale-105 transition-all duration-300 shadow-lg">
                  Contactanos
                </a>
              </div>
            </div>
          </div>
  
           
          
        </div>
      </div>
    </div>
  </template>
  
  <script setup>
  import { ref, onMounted, onUnmounted } from 'vue'
  
  // Desarrollo Web Timelapse
  const buildStep = ref(0)

  // WhatsApp helper
  const waPhone = '523312345678'
  const whatsAppUrl = (service) => {
    const msg = service ? `Hola, vengo del servicio: ${service}. Me gustaría más información.` : 'Hola, me gustaría más información.'
    return `https://wa.me/${waPhone}?text=${encodeURIComponent(msg)}`
  }
  
  // Social Media Animation
  const socialPosts = [
    { user: '@tuempresa', content: '¡Nuevo producto disponible! 🚀', likes: 245, comments: 32, shares: 18, time: '2h', icon: 'IG' },
    { user: '@tuempresa', content: 'Gracias por confiar en nosotros ❤️', likes: 189, comments: 28, shares: 12, time: '4h', icon: 'FB' },
    { user: '@tuempresa', content: 'Descubre nuestros servicios 💼', likes: 312, comments: 45, shares: 25, time: '1d', icon: 'TW' }
  ]
  const currentSocialPost = ref(socialPosts[0])
  const socialOffset = ref(0)
  const socialScale = ref(1)
  
  // Marketing Digital Animation
  const funnelStage = ref(0)
  // Ads simulation state
  const adImpressions = ref(45000)
  const adClicks = ref(2800)
  const ctr = ref(6.2)
  const budgetTotal = 50
  const spend = ref(12)
  const budgetPct = ref(24)
  const adVariant = ref('A')
  const channels = ref([
    { name: 'Feed', share: 45, color: '#6366f1' },
    { name: 'Stories', share: 30, color: '#ec4899' },
    { name: 'Search', share: 15, color: '#f59e0b' },
    { name: 'Video', share: 10, color: '#22d3ee' }
  ])
  const adConversions = ref(156)
  const cpa = ref(8.75)
  const creators = ref([
    { name: '@brandpartner_mx', platform: 'IG', followers: 120, match: 92, skin: '#f2d6c9', hair: '#3b3b3b', hairStyle: 'short', tagBg: '#fee2e2', tagFg: '#9f1239' }, // hombre piel clara
    { name: '@lifestyle_afro', platform: 'TT', followers: 140, match: 88, skin: '#4b2e22', hair: '#1f1b16', hairStyle: 'curly', tagBg: '#ccfbf1', tagFg: '#065f46' }, // mujer afrodescendiente (estilizada)
    { name: '@creativa_mx', platform: 'IG', followers: 95, match: 84, skin: '#f3e1d6', hair: '#6b4f3f', hairStyle: 'bun', tagBg: '#ede9fe', tagFg: '#4c1d95' } // mujer piel clara
  ])
  const selectedCreator = ref(0)
  const crowdPeople = ref([
    { skin: '#f2d6c9', hair: '#3b3b3b', hairStyle: 'short', shirt: '#fbbf24' },
    { skin: '#4b2e22', hair: '#1f1b16', hairStyle: 'curly', shirt: '#10b981' },
    { skin: '#f3e1d6', hair: '#6b4f3f', hairStyle: 'bun', shirt: '#a78bfa' },
    { skin: '#d1b8a0', hair: '#111827', hairStyle: 'short', shirt: '#ef4444' },
    { skin: '#e7c7b3', hair: '#9a3412', hairStyle: 'bun', shirt: '#3b82f6' },
    { skin: '#6b4f3f', hair: '#0b0b0b', hairStyle: 'curly', shirt: '#ec4899' },
    { skin: '#f2d6c9', hair: '#1f2937', hairStyle: 'short', shirt: '#22d3ee' },
    { skin: '#cfa18b', hair: '#7c2d12', hairStyle: 'bun', shirt: '#f59e0b' }
  ])
  // YouTube simulation
  const ytProgress = ref(0)
  // Carousel creators
  const creatorsCarousel = ref([
    { name: '@fashionmx', platform: 'IG', followers: 120, engagement: 4.2, colors: ['#ec4899','#f59e0b'] },
    { name: '@techgdl', platform: 'YT', followers: 85, engagement: 5.1, colors: ['#6366f1','#22d3ee'] },
    { name: '@foodielatam', platform: 'TT', followers: 140, engagement: 6.3, colors: ['#22d3ee','#10b981'] },
    { name: '@travelmx', platform: 'IG', followers: 95, engagement: 3.9, colors: ['#a78bfa','#ec4899'] },
    { name: '@gamingmx', platform: 'YT', followers: 110, engagement: 4.8, colors: ['#22d3ee','#3b82f6'] }
  ])
  const carouselIndex = ref(0)
  const cardWidthPx = 160
  const gapPx = 12
  const isCarouselHovered = ref(false)
  // Community simulation
  const cmMessages = ref([
    { id: 1, text: '¿Cuándo sale el nuevo producto?', time: '2m', reacts: 12, side: 'left' },
    { id: 2, text: 'Pronto! Esta semana 👀', time: '1m', reacts: 5, side: 'right' },
  ])
  const cmUnread = ref(3)
  const cmTyping = ref(false)
  const cmFeedRef = ref(null)
  // UGC hearts
  const ugcHearts = ref(Array.from({ length: 12 }, (_, i) => ({ id: i, x: Math.random()*80 + 10, delay: Math.floor(Math.random()*1200) })))
  // Influencer matching sim
  const imCreators = ref([
    { name: '@fashionmx', platform: 'IG', followers: 120, eng: 4.2, colors: ['#ec4899','#f59e0b'] },
    { name: '@techgdl', platform: 'YT', followers: 85, eng: 5.1, colors: ['#6366f1','#22d3ee'] },
    { name: '@foodielatam', platform: 'TT', followers: 140, eng: 6.3, colors: ['#22d3ee','#10b981'] }
  ])
  const imSelected = ref(0)
  const imProgress = ref(0)
  const imMetrics = ref([
    { name: 'Reach', value: 24000, display: '24K', pct: 65, trend: 'up', delta: '+12%' },
    { name: 'Engagement', value: 5.2, display: '5.2%', pct: 52, trend: 'up', delta: '+0.6%' },
    { name: 'CPM', value: 38, display: '$38', pct: 38, trend: 'down', delta: '-4%' },
    { name: 'CPL', value: 18, display: '$18', pct: 72, trend: 'down', delta: '-7%' }
  ])
  const imFollowers = ref(1268)
  const imEngagement = ref(4.3)
  const imReach = ref(18129)
  const imGoal = ref(20000)
  const imDelta = ref('+12%')
  
  // Branding Animation
  const brandColors = ['#E91E63', '#9C27B0', '#673AB7', '#3F51B5', '#2196F3', '#00BCD4', '#4CAF50', '#FF9800']
  const activeBrandColor = ref(0)
  
  // Analytics Animation
  const analyticsMetrics = ref([
    { name: 'Visitantes', value: 0, color: 'bg-blue-500' },
    { name: 'Conversiones', value: 0, color: 'bg-green-500' },
    { name: 'Engagement', value: 0, color: 'bg-purple-500' },
    { name: 'ROI', value: 0, color: 'bg-orange-500' }
  ])
  
  // Consultoría Animation
  const consultingSteps = ['Análisis Inicial', 'Estrategia Personalizada', 'Implementación', 'Optimización Continua']
  const currentConsultingStep = ref(0)
  // Media ON/OFF
  const mediaSites = ref([
    { id: 1, x: 18, y: 32, active: true },
    { id: 2, x: 46, y: 22, active: false },
    { id: 3, x: 62, y: 48, active: true },
    { id: 4, x: 35, y: 65, active: false },
    { id: 5, x: 78, y: 34, active: true },
  ])
  const mediaCoverage = ref(40)
  
  let intervals = []
  
  onMounted(() => {
    // Timelapse build sequence (Navbar → Hero → CTAs → Cards → Footer)
    const runBuild = () => {
      buildStep.value = 0
      setTimeout(() => buildStep.value = 1, 200)   // navbar container
      setTimeout(() => buildStep.value = 2, 600)   // brand + nav pills
      setTimeout(() => buildStep.value = 3, 1100)  // hero container
      setTimeout(() => buildStep.value = 4, 1500)  // title + subtitle
      setTimeout(() => buildStep.value = 5, 1900)  // CTAs
      setTimeout(() => buildStep.value = 6, 2400)  // cards row container
      setTimeout(() => buildStep.value = 7, 2800)  // card contents
      setTimeout(() => buildStep.value = 8, 3400)  // footer
    }
    runBuild()
    intervals.push(setInterval(() => {
      runBuild()
    }, 6500))
  
    // Social Media Animation
    intervals.push(setInterval(() => {
      socialOffset.value = -50
      socialScale.value = 0.9
      setTimeout(() => {
        const currentIndex = socialPosts.findIndex(post => post === currentSocialPost.value)
        currentSocialPost.value = socialPosts[(currentIndex + 1) % socialPosts.length]
        socialOffset.value = 0
        socialScale.value = 1
      }, 300)
    }, 4000))
  
    // Marketing Funnel Animation
    intervals.push(setInterval(() => {
      funnelStage.value = 0
      setTimeout(() => funnelStage.value = 1, 500)
      setTimeout(() => funnelStage.value = 2, 1000)
      setTimeout(() => funnelStage.value = 3, 1500)
    }, 5000))

    // Ads Simulation Animation
    intervals.push(setInterval(() => {
      // Randomly vary channel shares but keep sum ≈ 100
      const jitter = () => (Math.random() - 0.5) * 6
      let total = 0
      channels.value = channels.value.map(ch => ({ ...ch, share: Math.max(5, Math.min(70, Math.round(ch.share + jitter()))) }))
      total = channels.value.reduce((s, ch) => s + ch.share, 0)
      channels.value = channels.value.map(ch => ({ ...ch, share: Math.round((ch.share / total) * 100) }))
      // Random walk for KPIs
      adImpressions.value = Math.max(10000, adImpressions.value + Math.floor((Math.random()-0.5)*4000))
      adClicks.value = Math.max(500, adClicks.value + Math.floor((Math.random()-0.5)*300))
      ctr.value = Math.min(15, Math.max(0.5, (adClicks.value / Math.max(1, adImpressions.value)) * 100))
      adConversions.value = Math.max(50, adConversions.value + Math.floor((Math.random()-0.5)*20))
      cpa.value = Math.max(2, Math.min(50, (spend.value * 1000) / Math.max(1, adConversions.value)))
      spend.value = Math.min(budgetTotal, Math.max(0, spend.value + (Math.random()*3)))
      budgetPct.value = Math.min(100, Math.round((spend.value / budgetTotal) * 100))
    }, 2500))

    // Talent selection animation
    intervals.push(setInterval(() => {
      selectedCreator.value = (selectedCreator.value + 1) % creators.value.length
    }, 2800))

    // Carousel auto-scroll
    intervals.push(setInterval(() => {
      if (isCarouselHovered.value) return
      if (carouselIndex.value < creatorsCarousel.value.length - 1) {
        carouselIndex.value += 1
      } else {
        // pausa breve al final para que se sienta natural
        setTimeout(() => {
          carouselIndex.value = 0
        }, 900)
      }
    }, 1800))

    // YouTube progress animation
    intervals.push(setInterval(() => {
      ytProgress.value = (ytProgress.value + 5) % 100
    }, 500))
  
    // Branding Animation
    intervals.push(setInterval(() => {
      activeBrandColor.value = (activeBrandColor.value + 1) % brandColors.length
    }, 2500))
  
    // Analytics Animation
    intervals.push(setInterval(() => {
      analyticsMetrics.value = analyticsMetrics.value.map(metric => ({
        ...metric,
        value: Math.floor(Math.random() * 85) + 15
      }))
    }, 3500))
  
    // Consulting Animation
    intervals.push(setInterval(() => {
      currentConsultingStep.value = (currentConsultingStep.value + 1) % consultingSteps.length
    }, 2800))

    // Media sites animation
    intervals.push(setInterval(() => {
      mediaSites.value = mediaSites.value.map(s => ({ ...s, active: Math.random() > 0.5 }))
      mediaCoverage.value = Math.round((mediaSites.value.filter(s => s.active).length / mediaSites.value.length) * 100)
    }, 2200))

    // Community feed animation
    intervals.push(setInterval(() => {
      cmTyping.value = true
      setTimeout(() => {
        const samples = [
          { text: '¿Tienen envíos a todo México?', side: 'left' },
          { text: 'Contenido épico 🔥', side: 'left' },
          { text: 'Gracias por responder rápido 🙌', side: 'left' },
          { text: 'Agendando post para mañana 10:00', side: 'right' },
        ]
        const pick = samples[Math.floor(Math.random()*samples.length)]
        cmMessages.value = [...cmMessages.value, { id: Date.now(), text: pick.text, time: 'ahora', reacts: Math.floor(Math.random()*20), side: pick.side }]
        cmTyping.value = false
        cmUnread.value = Math.max(0, cmUnread.value - 1)
        requestAnimationFrame(() => {
          if (cmFeedRef.value) cmFeedRef.value.scrollTop = cmFeedRef.value.scrollHeight
        })
      }, 800)
    }, 2600))
    // Hearts refresh
    intervals.push(setInterval(() => {
      ugcHearts.value = Array.from({ length: 12 }, (_, i) => ({ id: Date.now()+i, x: Math.random()*80 + 10, delay: Math.floor(Math.random()*1200) }))
    }, 3000))
    // IM metrics pulse
    intervals.push(setInterval(() => {
      imMetrics.value = imMetrics.value.map(m => {
        const jitter = (Math.random()-0.5) * 6
        const pct = Math.min(100, Math.max(5, m.pct + jitter))
        const value = m.name === 'Engagement' ? Math.max(0.5, (pct/10)).toFixed(1) : Math.round(pct * 0.6)
        const display = m.name === 'Engagement' ? `${value}%` : (m.name === 'Reach' ? `${value}K` : `$${value}`)
        const trend = Math.random() > 0.5 ? 'up' : 'down'
        const delta = (trend === 'up' ? '+' : '-') + (Math.floor(Math.random()*9)+1) + '%'
        return { ...m, pct, display, trend, delta }
      })
    }, 1200))
    intervals.push(setInterval(() => {
      // Followers and reach subtle motion
      imFollowers.value = Math.max(800, imFollowers.value + Math.floor((Math.random()-0.4)*25))
      imEngagement.value = Math.min(8, Math.max(1, imEngagement.value + (Math.random()-0.5)*0.2))
      imReach.value = Math.max(8000, imReach.value + Math.floor((Math.random()-0.4)*150))
    }, 1400))
  })
  
  onUnmounted(() => {
    intervals.forEach(interval => clearInterval(interval))
  })
  </script>
  
  <style scoped>
  .glass {
    background: rgba(255, 255, 255, 0.25);
    border-radius: 1.5rem; /* rounded-3xl */
    box-shadow: 0 8px 24px rgba(0, 0, 0, 0.03);
    border: 1px solid rgba(255, 255, 255, 0.2);
    backdrop-filter: blur(10px);
    -webkit-backdrop-filter: blur(10px);
  }
  /* Ads simulation */
  .ads-sim { display:flex; flex-direction:column; gap:12px; overflow:hidden; }
  .ads-header { font-weight: 700; color:#1f2937; }
  .ads-body { display:grid; grid-template-columns: 1fr 1fr; gap:12px; height:100%; }
  .channels { display:flex; flex-direction:column; gap:10px; }
  .channel-row { display:grid; grid-template-columns: 16px 1fr auto; gap:10px; align-items:center; }
  .channel-row .bar { grid-column: span 2; }
  .dot { width:12px; height:12px; border-radius:50%; }
  .kpis { display:flex; flex-direction:column; gap:10px; overflow:hidden; }
  .kpi { display:flex; align-items:center; justify-content:space-between; gap:10px; background:#fff; border:1px solid rgba(0,0,0,0.06); border-radius:10px; padding:10px 12px; box-shadow: 0 6px 20px rgba(0,0,0,0.05); width:100%; box-sizing:border-box; }
  .kpi .val { font-weight:700; color:#111827; }
  .bar { width:100%; height:8px; background: #e5e7eb; border-radius:9999px; overflow:hidden; }
  .bar .fill { height:100%; background: linear-gradient(90deg, #6366f1, #ec4899); width:0%; transition: width .8s ease; }
  .bar.budget .fill { background: linear-gradient(90deg, #10b981, #f59e0b); }

  /* Talent simulation */
  .talent-sim { display:grid; grid-template-columns: repeat(2, 1fr); gap:12px; height:100%; }
  .talent-card { display:flex; align-items:center; gap:10px; background:#fff; border:1px solid rgba(0,0,0,0.06); border-radius:14px; padding:10px; box-shadow: 0 6px 20px rgba(0,0,0,0.05); position:relative; transition: transform .3s ease, box-shadow .3s ease; overflow:hidden; }
  .talent-card.selected { transform: translateY(-2px); box-shadow: 0 10px 24px rgba(99,102,241,0.25); }
  .avatar { position:relative; width:48px; height:48px; border-radius:12px; background:#f8fafc; }
  .head { position:absolute; width:30px; height:30px; border-radius:50%; top:8px; left:9px; }
  .hair { position:absolute; top:6px; left:6px; right:6px; height:18px; border-radius:10px; }
  .hair.short { border-bottom-left-radius:2px; border-bottom-right-radius:2px; }
  .hair.curly { filter: drop-shadow(0 1px 0 rgba(0,0,0,0.1)); border-radius:12px; }
  .hair.bun { width:22px; height:22px; border-radius:50%; top:-2px; left:13px; }
  .eye { position:absolute; width:4px; height:4px; background:#111827; border-radius:50%; top:22px; }
  .eye.left { left:17px; }
  .eye.right { right:17px; }
  .info { display:flex; flex-direction:column; }
  .name { font-weight:700; color:#111827; line-height:1; }
  .meta { display:flex; align-items:center; gap:8px; font-size:12px; color:#6b7280; }
  .pill { padding:2px 8px; border-radius:9999px; font-weight:700; }
  .followers { font-weight:700; color:#111827; }
  .match { position:absolute; right:10px; top:10px; font-size:12px; font-weight:700; color:#10b981; }

  /* Crowd sim */
  @keyframes sway { 0%,100%{ transform: translateY(0); } 50%{ transform: translateY(-2px); } }
  .crowd-sim { position:absolute; inset:0; display:grid; grid-template-columns: repeat(4, 1fr); grid-auto-rows: minmax(80px, 1fr); gap:10px; padding:6px; }
  .person { position:relative; animation: sway 4s ease-in-out var(--delay) infinite; }
  .shirt { position:absolute; bottom:0; left:0; right:0; height:50%; border-bottom-left-radius:10px; border-bottom-right-radius:10px; border-radius:12px; }
  .head-wrap { position:absolute; width:60%; aspect-ratio:1/1; left:20%; top:8%; }
  .head { position:absolute; width:100%; height:100%; border-radius:40% 40% 50% 50%; }
  .hair-layer { position:absolute; top:-6%; left:-6%; right:-6%; height:55%; border-radius:40% 40% 30% 30%; }
  .eye { position:absolute; width:5px; height:5px; background:#111827; border-radius:50%; top:45%; }
  .eye.left { left:30%; }
  .eye.right { right:30%; }
  .smile { position:absolute; width:36%; height:18%; border:3px solid transparent; border-top-color:#111827; border-radius:0 0 100% 100%; left:32%; top:58%; }
  .arrow-rise { position:absolute; width:80px; height:80px; right:8px; bottom:8px; border-right:10px solid #fff; border-top:10px solid #fff; transform: rotate(45deg); opacity:.6; }

  /* Carousel */
  .creator-carousel { position:relative; height:100%; overflow:hidden; }
  .creator-track { position:absolute; top:50%; transform: translateY(-50%); display:flex; gap:12px; padding:0 12px; left:0; right:0; translate: var(--offsetX, 0) 0; transition: translate .6s ease; }
  .creator-card { width:160px; min-width:160px; background:#fff; border:1px solid rgba(0,0,0,0.06); border-radius:16px; padding:10px; box-shadow: 0 6px 20px rgba(0,0,0,0.06); display:flex; flex-direction:column; gap:8px; }
  .creator-top { display:flex; align-items:center; justify-content:space-between; }
  .avatar-grad { width:42px; height:42px; border-radius:12px; }
  .platform-pill { font-size:12px; padding:2px 8px; border-radius:9999px; background:#f3f4f6; color:#111827; font-weight:700; }
  .creator-name { font-weight:700; color:#111827; white-space:nowrap; overflow:hidden; text-overflow:ellipsis; }
  .creator-stats { display:flex; justify-content:space-between; font-size:12px; color:#6b7280; }
  .creator-tags { display:flex; gap:6px; }
  .tag { font-size:10px; padding:2px 6px; border-radius:9999px; background:#f3f4f6; color:#374151; font-weight:600; }
  .mini-metric { display:flex; align-items:center; gap:8px; }
  .mini-label { font-size:10px; color:#6b7280; }
  .carousel-cta { position:absolute; left:50%; bottom:10px; transform: translateX(-50%); background: linear-gradient(90deg,#8b5cf6,#ec4899); color:#fff; border:none; border-radius:9999px; padding:8px 14px; font-weight:700; box-shadow: 0 10px 24px rgba(99,102,241,0.25); }
  .edge-mask { position:absolute; top:0; bottom:0; width:24px; pointer-events:none; }
  .edge-mask.left { left:0; background: linear-gradient(90deg, #fdf2f8, rgba(253,242,248,0)); }
  .edge-mask.right { right:0; background: linear-gradient(270deg, #fdf2f8, rgba(253,242,248,0)); }

  /* YouTube sim */
  .yt-sim { background:#0b0b0b; }
  .yt-screen { position:absolute; inset:0; display:flex; align-items:center; justify-content:center; background: radial-gradient(circle at 30% 30%, rgba(236,72,153,0.15), transparent 40%), radial-gradient(circle at 70% 70%, rgba(245,158,11,0.15), transparent 40%); }
  .yt-overlay { position:absolute; inset:0; background: linear-gradient(180deg, rgba(255,255,255,0.06), rgba(255,255,255,0)); pointer-events:none; }
  .yt-play { position:relative; width:84px; height:60px; background:#ff0000; border-radius:12px; box-shadow: 0 10px 30px rgba(255,0,0,0.4); display:flex; align-items:center; justify-content:center; }
  .yt-play .triangle { width:0; height:0; border-left:18px solid #fff; border-top:12px solid transparent; border-bottom:12px solid transparent; margin-left:6px; }
  .yt-pulse { position:absolute; width:84px; height:60px; border-radius:12px; box-shadow: 0 0 0 0 rgba(255,0,0,0.5); animation: pulseBox 2s infinite; }
  @keyframes pulseBox { 0%{ box-shadow:0 0 0 0 rgba(255,0,0,0.5);} 70%{ box-shadow:0 0 0 16px rgba(255,0,0,0);} 100%{ box-shadow:0 0 0 0 rgba(255,0,0,0);} }
  .yt-controls { position:absolute; left:0; right:0; bottom:0; padding:10px 12px; background: linear-gradient(180deg, rgba(0,0,0,0), rgba(0,0,0,0.6)); color:#fff; font-size:12px; }
  .progress { height:6px; background: rgba(255,255,255,0.25); border-radius:9999px; overflow:hidden; margin-bottom:8px; }
  .progress-fill { height:100%; background: linear-gradient(90deg,#ff0000,#f59e0b); transition: width .4s ease; }
  .meta { display:flex; align-items:center; justify-content:space-between; }
  .meta .left { display:flex; align-items:center; gap:8px; }
  .meta .right { display:flex; align-items:center; gap:10px; }
  .dot.live { width:8px; height:8px; background:#ff0000; border-radius:50%; animation: blink 1s infinite; }
  @keyframes blink { 0%,100%{ opacity:1;} 50%{ opacity:.2;} }
  .pill.subscribe { padding:2px 8px; border-radius:9999px; background:#ff0000; color:#fff; font-weight:800; }
  .story-ring { width:44px; height:44px; border-radius:9999px; background: conic-gradient(from 0deg, #ec4899, #a78bfa, #22d3ee, #ec4899); opacity:.85; box-shadow: 0 6px 16px rgba(0,0,0,0.15); }
  .ugc-hearts { position:absolute; inset:0; pointer-events:none; }
  @keyframes floatUp { 0%{ transform: translateY(0) scale(1); opacity:.9; } 100%{ transform: translateY(-80px) scale(1.4); opacity:0; } }
  .ugc-heart { position:absolute; bottom:20px; font-size:14px; animation: floatUp 1.8s ease-out infinite; }
  /* Influencer matching */
  .im-sim { color:#fff; }
  .brief { display:flex; gap:8px; margin-bottom:10px; }
  .chip { background: rgba(255,255,255,0.2); border:1px solid rgba(255,255,255,0.3); padding:4px 8px; border-radius:9999px; font-size:12px; }
  .im-list { display:grid; grid-template-columns: repeat(3, 1fr); gap:10px; }
  .im-card { background:#fff; color:#111827; border-radius:12px; padding:10px; border:1px solid rgba(0,0,0,0.06); box-shadow:0 6px 20px rgba(0,0,0,0.06); opacity:.85; transition: transform .3s ease, opacity .3s ease; }
  .im-card.active { transform: translateY(-2px); opacity:1; }
  .im-card .top { display:flex; align-items:center; gap:8px; }
  .im-card .avatar { width:36px; height:36px; border-radius:10px; }
  .im-card .name { font-weight:700; flex:1; }
  .im-card .platform { font-size:12px; background:#f3f4f6; border-radius:9999px; padding:2px 8px; }
  .im-card .stats { display:flex; justify-content:space-between; font-size:12px; color:#6b7280; margin-top:6px; }
  .im-progress { position:relative; height:8px; background:#e5e7eb; border-radius:9999px; overflow:hidden; margin-top:8px; }
  .im-progress .fill { position:absolute; inset:0; width:0%; background: linear-gradient(90deg,#8b5cf6,#ec4899); transition: width .4s ease; }
  .im-progress .label { position:absolute; right:8px; top:-18px; font-size:12px; font-weight:700; color:#fff; }
  /* IM metrics */
  .im-metrics .metric-card { background:#fff; color:#111827; border-radius:12px; padding:10px; border:1px solid rgba(0,0,0,0.06); box-shadow:0 6px 20px rgba(0,0,0,0.06); }
  .im-metrics .head { display:flex; align-items:center; justify-content:space-between; margin-bottom:6px; }
  .im-metrics .label { font-weight:700; }
  .im-metrics .value { font-weight:800; }
  .im-metrics .trend { font-size:11px; display:flex; align-items:center; gap:6px; margin-bottom:6px; }
  .im-metrics .trend.up { color:#16a34a; }
  .im-metrics .trend.down { color:#dc2626; }
  .im-metrics .trend .arrow { font-size:10px; }
  .im-metrics .trend .period { color:#6b7280; }
  .im-metrics .bar { height:8px; background:#e5e7eb; border-radius:9999px; overflow:hidden; }
  .im-metrics .fill { height:100%; background: linear-gradient(90deg,#8b5cf6,#ec4899); transition: width .5s ease; }
  .im-metrics .platforms { display:flex; gap:6px; }
  .pchip { font-size:12px; font-weight:800; padding:4px 8px; border-radius:9999px; color:#fff; }
  .pchip.ig { background: linear-gradient(90deg,#f59e0b,#ec4899,#8b5cf6); }
  .pchip.yt { background:#ff0000; }
  .pchip.tt { background: linear-gradient(90deg,#00f2ea,#ff0050); }
  /* Dashboard card */
  .im-metrics-frame { background: linear-gradient(135deg,#8b5cf6,#ec4899) padding-box, linear-gradient(135deg,#8b5cf6,#ec4899) border-box; border: 1px solid transparent; }
  .im-card { background:#fff; border-radius:12px; padding:14px; height:100%; box-shadow:0 8px 24px rgba(0,0,0,0.08); display:flex; flex-direction:column; gap:12px; }
  .im-header { display:flex; align-items:center; justify-content:space-between; }
  .im-header .title { font-weight:800; color:#111827; }
  .im-header .dot { width:10px; height:10px; border-radius:50%; }
  .im-header .dot.green { background:#10b981; }
  .im-top { display:grid; grid-template-columns: repeat(2, minmax(0,1fr)); gap:12px; }
  .stat-card { background: linear-gradient(180deg,#faf5ff,#fff); border:1px solid #f1f5f9; border-radius:10px; padding:10px; }
  .stat-card .label { font-size:12px; color:#6b7280; }
  .stat-card .value { font-weight:800; font-size:20px; color:#111827; }
  .reach-card { background: linear-gradient(180deg,#fdf2f8,#fff); border:1px solid #f1f5f9; border-radius:10px; padding:10px; }
  .reach-card .label { font-size:12px; color:#6b7280; }
  .reach-card .value { font-weight:800; font-size:20px; color:#111827; margin-bottom:6px; }
  .reach-card .bar { height:8px; background:#e5e7eb; border-radius:9999px; overflow:hidden; }
  .reach-card .fill { height:100%; background: linear-gradient(90deg,#ec4899,#a78bfa); transition: width .6s ease; }
  .im-footer { display:flex; align-items:center; justify-content:space-between; font-size:12px; color:#6b7280; }
  /* Media sim */
  .media-sim { background:#fff; overflow:hidden; }
  .map { position:absolute; inset:0; background: radial-gradient(circle at 20% 30%, rgba(236,72,153,0.12), transparent 40%), radial-gradient(circle at 70% 60%, rgba(245,158,11,0.12), transparent 40%); }
  .map::before { content:""; position:absolute; left:8px; right:8px; top:8px; bottom:30px; background: url('/mexico.png') no-repeat center; background-size: 140% auto; opacity:.28; filter: drop-shadow(0 6px 16px rgba(0,0,0,0.12)); }
  .site { position:absolute; transform: translate(-50%,-50%); }
  .panel { width:28px; height:18px; border-radius:4px; background: linear-gradient(135deg,#f59e0b,#ec4899); opacity:.4; box-shadow: 0 4px 12px rgba(0,0,0,0.15); transition: opacity .3s ease, transform .3s ease; }
  .site.active .panel { opacity:1; transform: translateY(-2px); }
  .pin { position:absolute; left:50%; top:100%; width:8px; height:8px; background:#10b981; border-radius:50%; transform: translate(-50%,6px); box-shadow:0 0 0 0 rgba(16,185,129,0.6); animation: pulseDot 1.8s infinite; }
  @keyframes pulseDot { 0%{ box-shadow:0 0 0 0 rgba(16,185,129,0.6);} 70%{ box-shadow:0 0 0 10px rgba(16,185,129,0);} 100%{ box-shadow:0 0 0 0 rgba(16,185,129,0);} }
  .legend { position:absolute; top:8px; left:8px; display:flex; gap:12px; background:#ffffffcc; padding:6px 8px; border-radius:10px; font-size:12px; }
  .legend .item { display:flex; align-items:center; gap:6px; }
  .led { width:10px; height:10px; border-radius:50%; }
  .led.on { background:#10b981; }
  .led.off { background:#9ca3af; }
  .booking { position:absolute; left:8px; right:8px; bottom:8px; background:#ffffffcc; padding:6px 8px; border-radius:10px; }
  .booking .label { font-size:12px; color:#374151; margin-bottom:4px; }
  .booking .bar { height:6px; background:#e5e7eb; border-radius:9999px; overflow:hidden; }
  .booking .fill { height:100%; background: linear-gradient(90deg,#a78bfa,#ec4899); transition: width .5s ease; }
  /* CM sim */
  .cm-sim { display:flex; flex-direction:column; height:100%; background:#ffffffaa; backdrop-filter: blur(2px); border-radius:14px; overflow:hidden; box-shadow: 0 6px 20px rgba(0,0,0,0.05); }
  .cm-header { display:flex; align-items:center; gap:8px; padding:8px 10px; background: linear-gradient(90deg,#8b5cf6,#ec4899); color:#fff; font-weight:800; }
  .cm-avatar { width:24px; height:24px; border-radius:50%; background:#fff; }
  .cm-title { flex:1; }
  .cm-badge { background:#fff; color:#8b5cf6; border-radius:9999px; padding:2px 8px; font-size:12px; }
  .cm-feed { flex:1; overflow:auto; padding:10px; display:flex; flex-direction:column; gap:8px; }
  .cm-bubble { max-width:75%; border-radius:12px; padding:8px 10px; box-shadow:0 6px 20px rgba(0,0,0,0.05); background:#fff; }
  .cm-bubble.right { align-self:flex-end; background:#f3e8ff; }
  .cm-meta { font-size:10px; color:#6b7280; margin-top:2px; }
  .cm-input { display:flex; gap:8px; padding:8px 10px; background:#f8fafc; }
  .cm-pill { padding:6px 10px; border-radius:9999px; background:#eef2ff; color:#3730a3; font-weight:700; font-size:12px; }
  .typing { display:flex; align-items:center; gap:3px; background:#f3f4f6; }
  .typing span { width:6px; height:6px; border-radius:50%; background:#9ca3af; animation: dot 1.3s infinite; }
  .typing span:nth-child(2){ animation-delay:.15s; }
  .typing span:nth-child(3){ animation-delay:.3s; }
  @keyframes dot { 0%,80%,100%{ opacity:.2; transform: translateY(0);} 40%{ opacity:1; transform: translateY(-2px);} }
  /* Timelapse styles */
  .page-sim { display:flex; flex-direction:column; background:#ffffff; }
  .nav-sim { display:flex; align-items:center; justify-content:space-between; padding:12px 16px; background:rgba(0,0,0,0.03); border-bottom:1px solid rgba(0,0,0,0.06); opacity:0; transform: translateY(-8px); transition: all .5s ease; }
  .nav-sim.is-visible { opacity:1; transform: translateY(0); }
  .brand-sim { width:96px; height:24px; background: linear-gradient(90deg,#ec4899,#f59e0b); border-radius:6px; opacity:0; transform: scale(.96); transition: all .4s ease .1s; }
  .brand-sim.is-visible { opacity:1; transform: scale(1); }
  .nav-links { display:flex; gap:10px; }
  .nav-pill { width:64px; height:24px; background: linear-gradient(90deg, rgba(168,85,247,0.22), rgba(236,72,153,0.22), rgba(245,158,11,0.22)); border-radius:9999px; opacity:0; transform: translateY(-6px); transition: all .4s ease .15s; }
  .nav-pill.is-visible { opacity:1; transform: translateY(0); }
  .hero-sim { padding:20px; display:flex; flex-direction:column; gap:10px; opacity:0; transform: translateY(12px); transition: all .5s ease; }
  .hero-sim.is-visible { opacity:1; transform: translateY(0); }
  .hero-title-sim { height:28px; width:60%; background: rgba(17,24,39,0.9); border-radius:8px; opacity:0; transform: translateY(6px); transition: all .45s ease .1s; }
  .hero-title-sim.is-visible { opacity:1; transform: translateY(0); }
  .hero-sub-sim { height:16px; width:80%; background: rgba(17,24,39,0.2); border-radius:8px; opacity:0; transform: translateY(6px); transition: all .45s ease .15s; }
  .hero-sub-sim.is-visible { opacity:1; transform: translateY(0); }
  .hero-cta-row { display:flex; gap:10px; margin-top:8px; }
  .cta-sim { height:36px; width:140px; border-radius:9999px; opacity:0; transform: translateY(8px); transition: all .45s ease .2s; }
  .cta-sim.primary { background: linear-gradient(90deg,#ec4899,#f59e0b); }
  .cta-sim.ghost { background: rgba(17,24,39,0.08); }
  .cta-sim.is-visible { opacity:1; transform: translateY(0); }
  .cards-row { display:grid; grid-template-columns: repeat(3, 1fr); gap:12px; padding:16px 20px; opacity:0; transform: translateY(12px); transition: all .5s ease; }
  .cards-row.is-visible { opacity:1; transform: translateY(0); }
  .card-sim { background: #ffffff; border:1px solid rgba(0,0,0,0.06); box-shadow: 0 6px 20px rgba(0,0,0,0.06); border-radius:14px; padding:10px; display:flex; flex-direction:column; gap:8px; opacity:0; transform: scale(.98); transition: all .45s ease .1s; }
  .card-sim.is-visible { opacity:1; transform: scale(1); }
  .card-media { height:64px; border-radius:10px; background: linear-gradient(180deg, rgba(168,85,247,0.35), rgba(236,72,153,0.25)); }
  .card-title { height:16px; width:70%; border-radius:6px; background: rgba(17,24,39,0.7); }
  .card-text { height:12px; width:90%; border-radius:6px; background: rgba(17,24,39,0.12); }
  .footer-sim { margin-top:auto; padding:14px 20px; display:grid; grid-template-columns: repeat(3,1fr); gap:10px; background: rgba(0,0,0,0.03); border-top:1px solid rgba(0,0,0,0.06); opacity:0; transform: translateY(8px); transition: all .5s ease; }
  .footer-sim.is-visible { opacity:1; transform: translateY(0); }
  .footer-block { height:10px; background: rgba(17,24,39,0.18); border-radius:8px; }
  </style>

