<template>
  <div class="min-h-screen bg-white overflow-x-hidden">

    <header class="fixed top-0 w-full bg-white/90 backdrop-blur-md z-50 border-b border-gray-100">
      <nav class="container mx-auto px-4 py-0">
        <div class="flex items-center justify-between">
          <div class="flex items-center space-x-2">
            <img src="/mvp_logo.svg" alt="MVP DIGITAL" class="h-24 sm:h-28 md:h-32 lg:h-36 xl:h-40 w-auto" />
          </div>
          
          <div class="hidden md:flex items-center space-x-10">
            <a href="#inicio" class="text-gray-800 hover:text-purple-600 transition-colors font-semibold text-lg md:text-xl lg:text-2xl">Inicio</a>
            <a href="#servicios" class="text-gray-800 hover:text-purple-600 transition-colors font-semibold text-lg md:text-xl lg:text-2xl">Servicios</a>
            <a href="#nosotros" class="text-gray-800 hover:text-purple-600 transition-colors font-semibold text-lg md:text-xl lg:text-2xl">Nosotros</a>
            <a href="#contacto" class="text-gray-800 hover:text-purple-600 transition-colors font-semibold text-lg md:text-xl lg:text-2xl">Contacto</a>
          </div>
          
          <div class="flex items-center gap-3">
            <a href="https://wa.me/523312345678?text=Hola,%20me%20gustar%C3%ADa%20m%C3%A1s%20informaci%C3%B3n." target="_blank" class="hidden md:inline-flex items-center bg-gradient-to-r from-purple-500 to-pink-500 text-white px-8 py-3 md:px-10 md:py-4 rounded-xl text-lg md:text-xl font-semibold shadow-lg hover:shadow-xl transform hover:scale-105 transition-all duration-300">
              <span>Contactanos</span>
            </a>
            <button @click="isMobileMenuOpen = !isMobileMenuOpen" class="md:hidden inline-flex items-center justify-center w-14 h-14 rounded-xl border border-gray-200 text-gray-700">
              <span v-if="!isMobileMenuOpen" class="text-2xl">☰</span>
              <span v-else class="text-2xl">✕</span>
            </button>
          </div>
        </div>
        <div v-if="isMobileMenuOpen" class="md:hidden mt-3">
          <div class="flex flex-col gap-2 bg-white rounded-xl border border-gray-100 p-5 shadow">
            <a href="#inicio" @click="isMobileMenuOpen=false" class="py-3 text-gray-700 hover:text-purple-600 transition-colors text-xl font-semibold">Inicio</a>
            <a href="#servicios" @click="isMobileMenuOpen=false" class="py-3 text-gray-700 hover:text-purple-600 transition-colors text-xl font-semibold">Servicios</a>
            <a href="#nosotros" @click="isMobileMenuOpen=false" class="py-3 text-gray-700 hover:text-purple-600 transition-colors text-xl font-semibold">Nosotros</a>
            <a href="#contacto" @click="isMobileMenuOpen=false" class="py-3 text-gray-700 hover:text-purple-600 transition-colors text-xl font-semibold">Contacto</a>
            <a href="https://wa.me/523312345678?text=Hola,%20me%20gustar%C3%ADa%20m%C3%A1s%20informaci%C3%B3n." target="_blank" class="mt-2 bg-gradient-to-r from-purple-500 to-pink-500 text-white px-6 py-4 rounded-xl text-xl font-bold shadow-lg">Contactanos</a>
          </div>
        </div>
      </nav>
    </header>

     
    <section id="inicio" class="pt-32 lg:pt-40 mt-30
     pb-20 relative">
      <!-- ReactBits-like Aurora/Beams background -->
      <div class="pointer-events-none absolute inset-0 -z-10 overflow-hidden">
        <div class="absolute -top-32 -left-32 w-[36rem] h-[36rem] bg-gradient-to-r from-purple-500 via-pink-500 to-orange-500 rounded-full blur-3xl opacity-30 animate-blob"></div>
        <div class="absolute top-1/4 -right-20 w-[28rem] h-[28rem] bg-gradient-to-r from-blue-500 to-purple-500 rounded-full blur-3xl opacity-25 animate-blob animation-delay-2000"></div>
        <div class="absolute -bottom-20 left-1/3 w-[32rem] h-[32rem] bg-gradient-to-r from-pink-500 to-orange-500 rounded-full blur-3xl opacity-20 animate-blob animation-delay-4000"></div>
      </div>
      <!-- Scrim de contraste para legibilidad del título (solo desktop) -->
      <div class="hidden lg:block absolute inset-y-0 left-0 w-2/3 bg-gradient-to-r from-white via-white/85 to-transparent z-10 pointer-events-none"></div>
      <div class="container mx-auto px-8 mt-4">
        <div class="flex flex-col lg:flex-row items-center xl:gap-24">
          <div class="space-y-7 animate-fade-in-up flex-1 max-w-3xl relative z-20 mx-auto">
            <h1 class="text-4xl sm:text-5xl md:text-6xl lg:text-7xl xl:text-8xl font-bold leading-tight tracking-tight text-center lg:text-left">
              <span class="text-gray-900 reveal-up block lg:whitespace-nowrap">La nueva generación del</span>
              <span class="block bg-gradient-to-r from-purple-600 via-pink-600 to-orange-500 bg-clip-text text-transparent reveal-up delay-200 lg:whitespace-nowrap">
                <TextType
                  text="Marketing Digital"
                  :typingSpeed="75"
                  :pauseDuration="1500"
                  :showCursor="true"
                  cursorCharacter="|"
                  :loop="true"
                />
              </span>
              <span class="text-gray-900 font-extrabold reveal-up delay-400 block lg:whitespace-nowrap">en México</span>
            </h1>
            
            <p class="text-xl text-muted-foreground mb-8 text-pretty max-w-2xl lg:mx-0 mx-auto reveal-up delay-600 text-center lg:text-left">
              Conectamos marcas con audiencias a través de estrategias auténticas, creativas y efectivas. Somos especialistas en emprendedores y PYMEs que buscan crecer, destacar y convertir.
            </p>
            
            
          </div>

          <div class="relative z-0 self-start lg:self-auto animate-fade-in-right w-fit hidden md:block  xl:ml-20 2xl:ml-32 shrink-0 scale-[1.03] lg:scale-125 lg:-mt-12 xl:-mt-12">
            <PhoneShowcase />
          </div>
        </div>
      </div>
    </section>

   
    <section id="historia" class="py-20">
      <div class="container mx-auto px-6">
        <div class="text-center mb-14">
          <h2 class="text-5xl lg:text-6xl font-extrabold mb-4">
            <span class="bg-gradient-to-r from-purple-600 via-pink-600 to-orange-500 bg-clip-text text-transparent">Nuestra Historia</span>
          </h2>
          <p class="text-gray-700 text-lg max-w-3xl mx-auto">Más de una década conectando marcas con audiencias de manera auténtica y estratégica</p>
        </div>

        <div class="grid lg:grid-cols-2 gap-10 items-stretch">
          <!-- Columna izquierda (MVP) → segundo en móvil, primero en desktop -->
          <div class="bg-white rounded-2xl shadow-xl p-7 lg:p-9 h-full order-2 lg:order-1">
            <h3 class="text-2xl font-extrabold text-gray-900 mb-2">MVP DIGITAL</h3>
            <p class="text-base text-gray-500 mb-6">Agencia de marketing integral</p>
            <p class="text-gray-700 text-base leading-relaxed mb-6">Nace de la visión estratégica de nuestro CEO, quien tras liderar campañas para grandes marcas en México decidió crear una agencia que conectara a las marcas con el mundo digital y tradicional de manera auténtica, estratégica y efectiva.</p>

            <div class="bg-gradient-to-r from-pink-50 to-orange-50 rounded-xl p-5 ring-1 ring-pink-100">
              <div class="flex items-center gap-3 mb-2">
                <span class="w-6 h-6 rounded-full bg-gradient-to-r from-pink-500 to-purple-500 inline-flex items-center justify-center text-white text-xs">✦</span>
                <span class="font-semibold text-gray-900">MVP MARKETING</span>
              </div>
              <p class="text-gray-700 text-sm">Nuestra división especializada en emprendedores y PYMEs aplica la experiencia acumulada en campañas nacionales e internacionales a negocios que buscan crecer desde cero.</p>
            </div>
          </div>

          <!-- Columna derecha → primero en móvil, segundo en desktop -->
          <div class="space-y-6 flex flex-col order-1 lg:order-2">
            <!-- Stats aligned cards (1 col en móvil) -->
            <div ref="histStatsRef" class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 gap-5 mb-3 items-stretch order-1">
              <div class="bg-white rounded-xl shadow-lg p-7 text-center flex flex-col justify-center min-h-[110px]">
                <div class="text-5xl font-extrabold bg-gradient-to-r from-purple-600 via-pink-600 to-orange-500 bg-clip-text text-transparent">{{ histYears }}+</div>
                <div class="text-sm text-gray-600 mt-1">Años de experiencia</div>
              </div>
              <div class="bg-white rounded-xl shadow-lg p-7 text-center flex flex-col justify-center min-h-[110px]">
                <div class="text-5xl font-extrabold bg-gradient-to-r from-purple-600 via-pink-600 to-orange-500 bg-clip-text text-transparent">{{ histProjects }}+</div>
                <div class="text-sm text-gray-600 mt-1">Proyectos exitosos</div>
              </div>
              <div class="bg-white rounded-xl shadow-lg p-7 text-center flex flex-col justify-center min-h-[110px]">
                <div class="text-5xl font-extrabold bg-gradient-to-r from-purple-600 via-pink-600 to-orange-500 bg-clip-text text-transparent">{{ histClients }}+</div>
                <div class="text-sm text-gray-600 mt-1">Clientes satisfechos</div>
              </div>
            </div>

            <!-- Misión (tercero en móvil, segundo en desktop) -->
            <div class="bg-white rounded-2xl shadow-xl p-7 order-3 lg:order-2">
              <div class="flex items-center gap-4 mb-3">
                <span class="w-10 h-10 rounded-xl bg-gradient-to-r from-pink-500 to-purple-500 inline-flex items-center justify-center text-white">🎯</span>
                <h4 class="text-xl font-extrabold text-gray-900">Nuestra Misión</h4>
              </div>
              <p class="text-gray-700 text-base leading-relaxed">Consolidar la presencia digital de marcas nacientes y posicionadas mediante estrategias efectivas, conectando con las audiencias correctas en México, USA y Latinoamérica.</p>
            </div>

            <!-- Visión (segundo en móvil, tercero en desktop) -->
            <div class="bg-white rounded-2xl shadow-xl p-7 order-2 lg:order-3">
              <div class="flex items-center gap-4 mb-3">
                <span class="w-10 h-10 rounded-xl bg-gradient-to-r from-purple-500 to-pink-500 inline-flex items-center justify-center text-white">📈</span>
                <h4 class="text-xl font-extrabold text-gray-900">Nuestra Visión</h4>
              </div>
              <p class="text-gray-700 text-base leading-relaxed">Ser la agencia líder en México en conectar marcas con comunidades digitales mediante contenido auténtico y colaboraciones estratégicas.</p>
            </div>
          </div>
        </div>
      </div>
    </section>

     
    <section id="servicios" class="py-0">
      <ServicesSection />
    </section>

   
    <ValuesSection />

    <FloatingContacts />

   

   
    <footer class="bg-gray-900 text-white py-12">
      <div class="container mx-auto px-6">
        <div class="grid md:grid-cols-4 gap-8">
          <div>
            <div class="flex items-center space-x-2 mb-4">
              <div class="w-10 h-10 bg-gradient-to-r from-purple-500 to-pink-500 rounded-lg flex items-center justify-center">
                <span class="text-white font-bold text-lg">M</span>
              </div>
              <span class="text-xl font-bold">MVP DIGITAL</span>
            </div>
            <p class="text-gray-400">
              Tu agencia de marketing digital en Guadalajara
            </p>
          </div>
          
          <div>
            <h4 class="text-lg font-semibold mb-4">Servicios</h4>
            <ul class="space-y-2 text-gray-400">
              <li>Desarrollo Web</li>
              <li>Social Media</li>
              <li>Marketing Digital</li>
              <li>Branding</li>
            </ul>
          </div>
          
          <div>
            <h4 class="text-lg font-semibold mb-4">Contacto</h4>
            <ul class="space-y-2 text-gray-400">
              <li>mvpdigital.gdl@gmail.com</li>
              <li>+52 33 1234 5678</li>
              <li>Guadalajara, México</li>
            </ul>
          </div>
          
          <div>
            <h4 class="text-lg font-semibold mb-4">Síguenos</h4>
            <div class="flex space-x-4">
              <a href="#" class="w-10 h-10 bg-gradient-to-r from-purple-500 to-pink-500 rounded-full flex items-center justify-center hover:scale-110 transition-transform">
                <span class="text-sm">f</span>
              </a>
              <a href="#" class="w-10 h-10 bg-gradient-to-r from-purple-500 to-pink-500 rounded-full flex items-center justify-center hover:scale-110 transition-transform">
                <span class="text-sm">ig</span>
              </a>
              <a href="#" class="w-10 h-10 bg-gradient-to-r from-purple-500 to-pink-500 rounded-full flex items-center justify-center hover:scale-110 transition-transform">
                <span class="text-sm">tw</span>
              </a>
            </div>
          </div>
        </div>
        
        <div class="border-t border-gray-800 mt-8 pt-8 text-center text-gray-400">
          <p>&copy; 2024 MVP DIGITAL. Todos los derechos reservados.</p>
        </div>
      </div>
    </footer>
  </div>
</template>

<script setup>
import PhoneShowcase from './components/PhoneShowcase.vue'
import ServicesSection from './components/ServicesSection.vue'
import { ref, onMounted, onUnmounted } from 'vue'
import ValuesSection from './components/ValuesSection.vue'
import TextType from './components/TextType.vue'
import FloatingContacts from './components/FloatingContacts.vue'

const isMobileMenuOpen = ref(false)
const services = ref([
  {
    icon: '🌐',
    title: 'Desarrollo Web',
    description: 'Sitios web modernos, responsivos y optimizados para convertir visitantes en clientes.'
  },
  {
    icon: '📱',
    title: 'Social Media',
    description: 'Gestión completa de redes sociales con contenido que conecta con tu audiencia.'
  },
  {
    icon: '🚀',
    title: 'Marketing Digital',
    description: 'Estrategias integrales de marketing digital para hacer crecer tu negocio online.'
  },
  {
    icon: '🎨',
    title: 'Branding',
    description: 'Creación de identidad visual única que refleje la esencia de tu marca.'
  },
  {
    icon: '📊',
    title: 'Analytics',
    description: 'Análisis detallado de métricas para optimizar tus campañas y resultados.'
  },
  {
    icon: '💡',
    title: 'Consultoría',
    description: 'Asesoría especializada para definir la mejor estrategia digital para tu empresa.'
  }
])

// Historia counters
const histYears = ref(0)
const histProjects = ref(0)
const histClients = ref(0)
const histStatsRef = ref(null)

onMounted(() => {
  // Animated counters when stats are in viewport
  const runCounters = () => {
    const duration = 1200
    const start = performance.now()
    const animate = (now) => {
      const p = Math.min(1, (now - start) / duration)
      histYears.value = Math.floor(12 * p)
      histProjects.value = Math.floor(500 * p)
      histClients.value = Math.floor(200 * p)
      if (p < 1) requestAnimationFrame(animate)
    }
    requestAnimationFrame(animate)
  }

  const target = histStatsRef.value
  if (!target) {
    runCounters()
    return
  }
  const io = new IntersectionObserver((entries) => {
    entries.forEach(e => {
      if (e.isIntersecting) {
        runCounters()
        io.disconnect()
      }
    })
  }, { threshold: 0.3 })
  io.observe(target)
})

onMounted(() => {
  // Add scroll animations
  const observerOptions = {
    threshold: 0.1,
    rootMargin: '0px 0px -50px 0px'
  }
  
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        entry.target.classList.add('animate-in')
      }
    })
  }, observerOptions)
  
  document.querySelectorAll('.animate-fade-in-up').forEach(el => {
    observer.observe(el)
  })
})

onUnmounted(() => {})
</script>

<style scoped>
/* Visible gradient text helper to avoid inherited text-transparent issues */
.gradient-text {
  background-image: linear-gradient(90deg, #7c3aed, #ec4899, #f59e0b);
  -webkit-background-clip: text;
  background-clip: text;
  color: transparent;
  background-size: 200% 200%;
  animation: gradientShift 6s ease-in-out infinite alternate;
}
@keyframes gradientShift {
  0% { background-position: 0% 50%; }
  100% { background-position: 100% 50%; }
}
@keyframes revealUp {
  0% { opacity: 0; transform: translateY(18px); }
  100% { opacity: 1; transform: translateY(0); }
}
.reveal-up { opacity: 0; animation: revealUp .7s ease forwards; }
.reveal-up.delay-200 { animation-delay: .2s; }
.reveal-up.delay-400 { animation-delay: .4s; }
.reveal-up.delay-600 { animation-delay: .6s; }
@keyframes gradientShift {
  0% { background-position: 0% 50%; }
  100% { background-position: 100% 50%; }
}
@keyframes revealUp {
  0% { opacity: 0; transform: translateY(18px); }
  100% { opacity: 1; transform: translateY(0); }
}
.reveal-up { opacity: 0; animation: revealUp .7s ease forwards; }
.reveal-up.delay-200 { animation-delay: .2s; }
.reveal-up.delay-400 { animation-delay: .4s; }
.reveal-up.delay-600 { animation-delay: .6s; }
.gradient-animated { background-size: 200% 200%; animation: gradientShift 6s ease-in-out infinite alternate; }
@keyframes blobMove {
  0%, 100% {
    transform: translate3d(0, 0, 0) scale(1);
  }
  33% {
    transform: translate3d(20px, -30px, 0) scale(1.05);
  }
  66% {
    transform: translate3d(-25px, 15px, 0) scale(0.98);
  }
}

.animate-blob {
  animation: blobMove 12s ease-in-out infinite;
}
.animation-delay-2000 { animation-delay: 2s; }
.animation-delay-4000 { animation-delay: 4s; }
@keyframes fadeInUp {
  from {
    opacity: 0;
    transform: translateY(30px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

@keyframes fadeInRight {
  from {
    opacity: 0;
    transform: translateX(30px);
  }
  to {
    opacity: 1;
    transform: translateX(0);
  }
}

@keyframes float {
  0%, 100% {
    transform: translateY(0px);
  }
  50% {
    transform: translateY(-20px);
  }
}

@keyframes floatDelayed {
  0%, 100% {
    transform: translateY(0px);
  }
  50% {
    transform: translateY(-15px);
  }
}

.animate-fade-in-up {
  animation: fadeInUp 0.8s ease-out forwards;
}

.animate-fade-in-right {
  animation: fadeInRight 0.8s ease-out 0.3s forwards;
  opacity: 0;
}

.animate-float {
  animation: float 6s ease-in-out infinite;
}

.animate-float-delayed {
  animation: floatDelayed 8s ease-in-out infinite;
  animation-delay: 2s;
}

.animate-in {
  animation: fadeInUp 0.8s ease-out forwards;
}

/* Smooth scrolling */
html {
  scroll-behavior: smooth;
}

/* Custom gradient text */
.bg-clip-text {
  -webkit-background-clip: text;
  background-clip: text;
}
</style>
