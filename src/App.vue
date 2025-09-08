<template>
  <div class="min-h-screen bg-white overflow-x-hidden">
     Header 
    <header class="fixed top-0 w-full bg-white/90 backdrop-blur-md z-50 border-b border-gray-100">
      <nav class="container mx-auto px-6 py-4">
        <div class="flex items-center justify-between">
          <div class="flex items-center space-x-2">
            <img src="/mvp_logo.svg" alt="MVP DIGITAL" class="h-10 w-auto transform origin-left scale-125 sm:scale-125 md:scale-150 lg:scale-150" />
            
          </div>
          
          <div class="hidden md:flex items-center space-x-8">
            <a href="#inicio" class="text-gray-700 hover:text-purple-600 transition-colors">Inicio</a>
            <a href="#servicios" class="text-gray-700 hover:text-purple-600 transition-colors">Servicios</a>
            <a href="#nosotros" class="text-gray-700 hover:text-purple-600 transition-colors">Nosotros</a>
            <a href="#contacto" class="text-gray-700 hover:text-purple-600 transition-colors">Contacto</a>
          </div>
          
          <button class="bg-gradient-to-r from-purple-500 to-pink-500 text-white px-6 py-2 rounded-full hover:shadow-lg transform hover:scale-105 transition-all duration-300">
            Cotizar Ahora
          </button>
        </div>
      </nav>
    </header>

     Hero Section 
    <section id="inicio" class="pt-32 lg:pt-40 pb-20 relative">
      <!-- ReactBits-like Aurora/Beams background -->
      <div class="pointer-events-none absolute inset-0 -z-10 overflow-hidden">
        <div class="absolute -top-32 -left-32 w-[36rem] h-[36rem] bg-gradient-to-r from-purple-500 via-pink-500 to-orange-500 rounded-full blur-3xl opacity-30 animate-blob"></div>
        <div class="absolute top-1/4 -right-20 w-[28rem] h-[28rem] bg-gradient-to-r from-blue-500 to-purple-500 rounded-full blur-3xl opacity-25 animate-blob animation-delay-2000"></div>
        <div class="absolute -bottom-20 left-1/3 w-[32rem] h-[32rem] bg-gradient-to-r from-pink-500 to-orange-500 rounded-full blur-3xl opacity-20 animate-blob animation-delay-4000"></div>
      </div>
      <div class="container mx-auto px-8 mt-4">
        <div class="flex flex-col lg:flex-row items-start lg:items-center gap-10 lg:gap-14 xl:gap-24">
          <div class="space-y-7 animate-fade-in-up self-start flex-1 max-w-3xl">
            <h1 class="text-6xl lg:text-7xl xl:text-8xl font-bold leading-tight tracking-tight">
              <span class="text-gray-900 reveal-up block whitespace-nowrap">La nueva generación del</span>
              <span class="block bg-gradient-to-r from-purple-600 via-pink-600 to-orange-500 bg-clip-text text-transparent reveal-up delay-200 whitespace-nowrap">
                <TextType
                  text="Marketing Digital"
                  :typingSpeed="75"
                  :pauseDuration="1500"
                  :showCursor="true"
                  cursorCharacter="|"
                  :loop="true"
                />
              </span>
              <span class="text-gray-900 font-extrabold reveal-up delay-400 block whitespace-nowrap">en México</span>
            </h1>
            
            <p class="text-xl text-muted-foreground mb-8 text-pretty max-w-2xl lg:mx-0 mx-auto reveal-up delay-600">
              Conectamos marcas con audiencias a través de estrategias auténticas, creativas y efectivas. Somos especialistas en emprendedores y PYMEs que buscan crecer, destacar y convertir.
            </p>
            
            <div class="flex flex-col sm:flex-row gap-4">
              <button class="bg-gradient-to-r from-purple-500 to-pink-500 text-white px-8 py-4 rounded-full text-lg font-semibold hover:shadow-xl transform hover:scale-105 transition-all duration-300">
                Comenzar Proyecto
              </button>
              <button class="border-2 border-purple-500 text-purple-600 px-8 py-4 rounded-full text-lg font-semibold hover:bg-purple-50 transition-all duration-300">
                Ver Portfolio
              </button>
            </div>
          </div>

          <div class="relative self-start lg:self-auto animate-fade-in-right w-fit lg:ml-55 xl:ml-70 2xl:ml-80 shrink-0 scale-[1.03] lg:scale-125 lg:-mt-12 xl:-mt-12">
            <PhoneShowcase />
          </div>
        </div>
      </div>
    </section>

     Historia Section 
    <section id="historia" class="py-20">
      <div class="container mx-auto px-6">
        <div class="text-center mb-14">
          <h2 class="text-5xl lg:text-6xl font-extrabold mb-4">
            <span class="bg-gradient-to-r from-purple-600 via-pink-600 to-orange-500 bg-clip-text text-transparent">Nuestra Historia</span>
          </h2>
          <p class="text-gray-700 text-lg max-w-3xl mx-auto">Más de una década conectando marcas con audiencias de manera auténtica y estratégica</p>
        </div>

        <div class="grid lg:grid-cols-2 gap-10 items-stretch">
          <!-- Columna izquierda -->
          <div class="bg-white rounded-2xl shadow-xl p-7 lg:p-9 h-full">
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

          <!-- Columna derecha -->
          <div class="space-y-6">
            <!-- Stats aligned cards -->
            <div class="grid grid-cols-3 gap-5 mb-3 items-stretch">
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

            <!-- Misión -->
            <div class="bg-white rounded-2xl shadow-xl p-7">
              <div class="flex items-center gap-4 mb-3">
                <span class="w-10 h-10 rounded-xl bg-gradient-to-r from-pink-500 to-purple-500 inline-flex items-center justify-center text-white">🎯</span>
                <h4 class="text-xl font-extrabold text-gray-900">Nuestra Misión</h4>
              </div>
              <p class="text-gray-700 text-base leading-relaxed">Consolidar la presencia digital de marcas nacientes y posicionadas mediante estrategias efectivas, conectando con las audiencias correctas en México, USA y Latinoamérica.</p>
            </div>

            <!-- Visión -->
            <div class="bg-white rounded-2xl shadow-xl p-7">
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

     Services Section 
    <section id="servicios" class="py-0">
      <ServicesSection />
    </section>

     Valores Section 
    <ValuesSection />

     About Section 
    <section id="nosotros" class="py-20">
      <div class="container mx-auto px-6">
        <div class="grid lg:grid-cols-2 gap-12 items-center">
          <div class="space-y-8">
            <h2 class="--text-4xl lg:text-5xl font-bold">
              <span class="bg-gradient-to-r from-purple-600 to-pink-600 bg-clip-text text-transparent">
                Sobre MVP DIGITAL
              </span>
            </h2>
            
            <p class="text-lg text-gray-600 leading-relaxed">
              Somos una agencia de marketing digital con sede en Guadalajara, México. 
              Nos especializamos en crear estrategias digitales que impulsan el crecimiento 
              de empresas y emprendedores.
            </p>
            
            <div class="space-y-4">
              <div class="flex items-center space-x-4">
                <div class="w-12 h-12 bg-gradient-to-r from-purple-500 to-pink-500 rounded-full flex items-center justify-center">
                  <span class="text-white font-bold">✓</span>
                </div>
                <span class="text-lg text-gray-700">+5 años de experiencia</span>
              </div>
              <div class="flex items-center space-x-4">
                <div class="w-12 h-12 bg-gradient-to-r from-purple-500 to-pink-500 rounded-full flex items-center justify-center">
                  <span class="text-white font-bold">✓</span>
                </div>
                <span class="text-lg text-gray-700">+100 proyectos exitosos</span>
              </div>
              <div class="flex items-center space-x-4">
                <div class="w-12 h-12 bg-gradient-to-r from-purple-500 to-pink-500 rounded-full flex items-center justify-center">
                  <span class="text-white font-bold">✓</span>
                </div>
                <span class="text-lg text-gray-700">Equipo especializado</span>
              </div>
            </div>
          </div>
          
          <div class="relative">
            <div class="bg-gradient-to-r from-purple-500 to-pink-500 rounded-2xl p-8 text-white">
              <h3 class="text-2xl font-bold mb-4">Nuestra Misión</h3>
              <p class="text-lg opacity-90 mb-6">
                Ayudar a empresas y emprendedores a alcanzar sus objetivos comerciales 
                a través de estrategias de marketing digital innovadoras y efectivas.
              </p>
              
              <h3 class="text-2xl font-bold mb-4">Nuestra Visión</h3>
              <p class="text-lg opacity-90">
                Ser la agencia de marketing digital líder en México, reconocida por 
                nuestra creatividad, resultados y compromiso con el éxito de nuestros clientes.
              </p>
            </div>
          </div>
        </div>
      </div>
    </section>

     Contact Section 
    <section id="contacto" class="py-20 bg-gradient-to-r from-purple-600 via-pink-600 to-orange-500">
      <div class="container mx-auto px-6 text-center">
        <h2 class="text-4xl lg:text-5xl font-bold text-white mb-8">
          ¿Listo para impulsar tu negocio?
        </h2>
        <p class="text-xl text-white/90 mb-12 max-w-2xl mx-auto">
          Contáctanos hoy y descubre cómo podemos ayudarte a alcanzar tus objetivos digitales
        </p>
        
        <div class="flex flex-col sm:flex-row gap-6 justify-center items-center mb-12">
          <div class="flex items-center space-x-3 text-white">
            <span class="text-2xl">📧</span>
            <span class="text-lg">mvpdigital.gdl@gmail.com</span>
          </div>
          <div class="flex items-center space-x-3 text-white">
            <span class="text-2xl">📱</span>
            <span class="text-lg">+52 33 1234 5678</span>
          </div>
          <div class="flex items-center space-x-3 text-white">
            <span class="text-2xl">📍</span>
            <span class="text-lg">Guadalajara, México</span>
          </div>
        </div>
        
        <button class="bg-white text-purple-600 px-12 py-4 rounded-full text-lg font-bold hover:shadow-xl transform hover:scale-105 transition-all duration-300">
          Solicitar Cotización
        </button>
      </div>
    </section>

     Footer 
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

onMounted(() => {
  // Animated counters for historia section
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
