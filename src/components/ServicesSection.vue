<template>
    <div class="min-h-screen bg-white py-24">
      <div class="container mx-auto px-6">
         
        <div class="text-center mb-16">
          <h1 class="text-5xl lg:text-6xl font-bold mb-4">
            <span class="bg-gradient-to-r from-purple-600 via-pink-600 to-orange-500 bg-clip-text text-transparent">Nuestros Servicios</span>
          </h1>
          <p class="text-xl md:text-2xl text-gray-600">Soluciones integrales de marketing digital para hacer crecer tu negocio</p>
        </div>
  
          
        <div class="space-y-12">
           
          <div class="glass p-10 lg:p-12 hover:shadow-2xl transition-all duration-500">
            <div class="grid lg:grid-cols-2 gap-8 items-center">
              <div>
                <h3 class="text-4xl font-bold text-gray-900 mb-4">Desarrollo Web</h3>
                <p class="text-gray-700 mb-6 leading-relaxed">Sitios web modernos, responsivos y optimizados para convertir visitantes en clientes.</p>
                <ul class="space-y-3 mb-8">
                  <li class="flex items-center text-gray-700">
                    <span class="text-pink-500 mr-3 text-lg">→</span>
                    Diseño responsive y moderno
                  </li>
                  <li class="flex items-center text-gray-700">
                    <span class="text-pink-500 mr-3 text-lg">→</span>
                    Optimización SEO integrada
                  </li>
                  <li class="flex items-center text-gray-700">
                    <span class="text-pink-500 mr-3 text-lg">→</span>
                    Velocidad de carga optimizada
                  </li>
                </ul>
                <button class="bg-gradient-to-r from-pink-500 to-orange-500 text-white px-8 py-4 rounded-xl font-semibold hover:from-pink-600 hover:to-orange-600 transform hover:scale-105 transition-all duration-300 shadow-lg">
                  Empezar ahora
                </button>
              </div>
              <div class="w-full h-80 bg-gray-900 rounded-2xl p-6 relative overflow-hidden shadow-xl">
                <div class="text-green-400 font-mono text-sm leading-relaxed">
                  <div class="opacity-80">{{ codeLines.line1 }}</div>
                  <div class="ml-4 opacity-80">{{ codeLines.line2 }}</div>
                  <div class="ml-4 opacity-80">{{ codeLines.line3 }}</div>
                  <div class="ml-8 text-yellow-400 animate-pulse">{{ codeLines.activeElement }}</div>
                  <div class="ml-4 opacity-80">{{ codeLines.line4 }}</div>
                  <div class="opacity-80">{{ codeLines.line5 }}</div>
                </div>
                <div class="absolute bottom-4 right-4 w-3 h-3 bg-green-400 rounded-full animate-pulse"></div>
              </div>
            </div>
          </div>
  
            
          <div class="glass p-10 lg:p-12 hover:shadow-2xl transition-all duration-500">
            <div class="grid lg:grid-cols-2 gap-8 items-center">
              <div class="w-full h-80 bg-gradient-to-br from-purple-600 to-pink-600 rounded-2xl p-6 relative overflow-hidden shadow-xl">
                <div class="bg-white rounded-xl p-4 transform transition-all duration-700 ease-in-out" 
                     :style="{ transform: `translateY(${socialOffset}px) scale(${socialScale})` }">
                  <div class="flex items-center mb-3">
                    <div class="w-10 h-10 bg-gradient-to-r from-pink-500 to-purple-500 rounded-full mr-3 flex items-center justify-center">
                      <span class="text-white text-sm font-bold">{{ currentSocialPost.icon }}</span>
                    </div>
                    <div>
                      <div class="font-semibold text-gray-900">{{ currentSocialPost.user }}</div>
                      <div class="text-xs text-gray-500">{{ currentSocialPost.time }}</div>
                    </div>
                  </div>
                  <p class="text-gray-800 mb-3 text-sm">{{ currentSocialPost.content }}</p>
                  <div class="flex space-x-4 text-gray-500 text-xs">
                    <span class="flex items-center">
                      <span class="mr-1">❤️</span> {{ currentSocialPost.likes }}
                    </span>
                    <span class="flex items-center">
                      <span class="mr-1">💬</span> {{ currentSocialPost.comments }}
                    </span>
                    <span class="flex items-center">
                      <span class="mr-1">🔄</span> {{ currentSocialPost.shares }}
                    </span>
                  </div>
                </div>
              </div>
              <div>
                <h3 class="text-4xl font-bold text-gray-900 mb-4">Social Media</h3>
                <p class="text-gray-700 mb-6 leading-relaxed">Gestión completa de redes sociales con contenido que conecta con tu audiencia.</p>
                <ul class="space-y-3 mb-8">
                  <li class="flex items-center text-gray-700">
                    <span class="text-purple-500 mr-3 text-lg">→</span>
                    Contenido creativo y engagement
                  </li>
                  <li class="flex items-center text-gray-700">
                    <span class="text-purple-500 mr-3 text-lg">→</span>
                    Gestión de comunidades
                  </li>
                  <li class="flex items-center text-gray-700">
                    <span class="text-purple-500 mr-3 text-lg">→</span>
                    Análisis de métricas sociales
                  </li>
                </ul>
                <button class="bg-gradient-to-r from-purple-500 to-pink-500 text-white px-8 py-4 rounded-xl font-semibold hover:from-purple-600 hover:to-pink-600 transform hover:scale-105 transition-all duration-300 shadow-lg">
                  Empezar ahora
                </button>
              </div>
            </div>
          </div>
  
           
          <div class="glass p-10 lg:p-12 hover:shadow-2xl transition-all duration-500">
            <div class="grid lg:grid-cols-2 gap-8 items-center">
              <div>
                <h3 class="text-4xl font-bold text-gray-900 mb-4">Marketing Digital</h3>
                <p class="text-gray-700 mb-6 leading-relaxed">Estrategias integrales de marketing digital para hacer crecer tu negocio online.</p>
                <ul class="space-y-3 mb-8">
                  <li class="flex items-center text-gray-700">
                    <span class="text-orange-500 mr-3 text-lg">→</span>
                    Campañas publicitarias efectivas
                  </li>
                  <li class="flex items-center text-gray-700">
                    <span class="text-orange-500 mr-3 text-lg">→</span>
                    Email marketing automatizado
                  </li>
                  <li class="flex items-center text-gray-700">
                    <span class="text-orange-500 mr-3 text-lg">→</span>
                    Optimización de conversiones
                  </li>
                </ul>
                <button class="bg-gradient-to-r from-orange-500 to-red-500 text-white px-8 py-4 rounded-xl font-semibold hover:from-orange-600 hover:to-red-600 transform hover:scale-105 transition-all duration-300 shadow-lg">
                  Empezar ahora
                </button>
              </div>
              <div class="w-full h-80 bg-gradient-to-br from-orange-100 to-red-100 rounded-2xl p-6 relative shadow-xl">
                <div class="text-center">
                  <h4 class="text-xl font-bold text-gray-800 mb-6">Embudo de Conversión</h4>
                  <div class="space-y-4">
                    <div class="relative">
                      <div class="bg-orange-500 text-white py-3 px-6 rounded-lg font-semibold transition-all duration-1000 ease-out"
                           :style="{ width: funnelStage >= 1 ? '100%' : '20%', opacity: funnelStage >= 1 ? 1 : 0.3 }">
                        Visitantes: 10,000
                      </div>
                    </div>
                    <div class="relative">
                      <div class="bg-orange-600 text-white py-3 px-6 rounded-lg font-semibold transition-all duration-1000 ease-out"
                           :style="{ width: funnelStage >= 2 ? '75%' : '20%', opacity: funnelStage >= 2 ? 1 : 0.3 }">
                        Leads: 2,500
                      </div>
                    </div>
                    <div class="relative">
                      <div class="bg-red-500 text-white py-3 px-6 rounded-lg font-semibold transition-all duration-1000 ease-out"
                           :style="{ width: funnelStage >= 3 ? '50%' : '20%', opacity: funnelStage >= 3 ? 1 : 0.3 }">
                        Clientes: 500
                      </div>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
  
           
          <div class="glass p-10 lg:p-12 hover:shadow-2xl transition-all duration-500">
            <div class="grid lg:grid-cols-2 gap-8 items-center">
              <div class="w-full h-80 bg-gradient-to-br from-purple-100 to-pink-100 rounded-2xl p-6 relative shadow-xl">
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
              <div>
                <h3 class="text-4xl font-bold text-gray-900 mb-4">Branding</h3>
                <p class="text-gray-700 mb-6 leading-relaxed">Creación de identidad visual única que refleje la esencia de tu marca.</p>
                <ul class="space-y-3 mb-8">
                  <li class="flex items-center text-gray-700">
                    <span class="text-purple-500 mr-3 text-lg">→</span>
                    Diseño de logotipos únicos
                  </li>
                  <li class="flex items-center text-gray-700">
                    <span class="text-purple-500 mr-3 text-lg">→</span>
                    Paletas de colores estratégicas
                  </li>
                  <li class="flex items-center text-gray-700">
                    <span class="text-purple-500 mr-3 text-lg">→</span>
                    Manual de identidad corporativa
                  </li>
                </ul>
                <button class="bg-gradient-to-r from-purple-500 to-indigo-500 text-white px-8 py-4 rounded-xl font-semibold hover:from-purple-600 hover:to-indigo-600 transform hover:scale-105 transition-all duration-300 shadow-lg">
                  Empezar ahora
                </button>
              </div>
            </div>
          </div>
  
           
          <div class="glass p-10 lg:p-12 hover:shadow-2xl transition-all duration-500">
            <div class="grid lg:grid-cols-2 gap-8 items-center">
              <div>
                <h3 class="text-4xl font-bold text-gray-900 mb-4">Analytics</h3>
                <p class="text-gray-700 mb-6 leading-relaxed">Análisis detallado de métricas para optimizar tus campañas y resultados.</p>
                <ul class="space-y-3 mb-8">
                  <li class="flex items-center text-gray-700">
                    <span class="text-blue-500 mr-3 text-lg">→</span>
                    Reportes detallados de rendimiento
                  </li>
                  <li class="flex items-center text-gray-700">
                    <span class="text-blue-500 mr-3 text-lg">→</span>
                    Seguimiento de conversiones
                  </li>
                  <li class="flex items-center text-gray-700">
                    <span class="text-blue-500 mr-3 text-lg">→</span>
                    Insights accionables
                  </li>
                </ul>
                <button class="bg-gradient-to-r from-blue-500 to-cyan-500 text-white px-8 py-4 rounded-xl font-semibold hover:from-blue-600 hover:to-cyan-600 transform hover:scale-105 transition-all duration-300 shadow-lg">
                  Empezar ahora
                </button>
              </div>
              <div class="w-full h-80 bg-gradient-to-br from-blue-50 to-cyan-50 rounded-2xl p-6 shadow-xl">
                <div class="text-center mb-6">
                  <h4 class="text-xl font-bold text-gray-800">Métricas en Tiempo Real</h4>
                </div>
                <div class="space-y-6">
                  <div v-for="(metric, index) in analyticsMetrics" :key="index" class="flex justify-between items-center">
                    <span class="text-sm font-medium text-gray-700">{{ metric.name }}</span>
                    <div class="flex items-center">
                      <div class="w-32 bg-gray-200 rounded-full h-3 mr-3 overflow-hidden">
                        <div class="h-3 rounded-full transition-all duration-2000 ease-out"
                             :class="metric.color"
                             :style="{ width: `${metric.value}%` }">
                        </div>
                      </div>
                      <span class="text-sm font-bold text-gray-800 w-12">{{ metric.value }}%</span>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
  
           
          <div class="glass p-10 lg:p-12 hover:shadow-2xl transition-all duration-500">
            <div class="grid lg:grid-cols-2 gap-8 items-center">
              <div class="w-full h-80 bg-gradient-to-br from-indigo-100 to-purple-100 rounded-2xl p-6 shadow-xl">
                <div class="text-center">
                  <h4 class="text-xl font-bold text-gray-800 mb-6">Proceso de Consultoría</h4>
                  <div class="space-y-4">
                    <div v-for="(step, index) in consultingSteps" :key="index"
                         class="flex items-center p-4 rounded-xl h-10 transition-colors duration-500 ring-1"
                         :class="currentConsultingStep === index ? 'bg-indigo-500 text-white ring-indigo-300 shadow-md' : 'bg-white text-gray-700 ring-gray-200 shadow'">
                      <div class="w-7 h-7 rounded-full mr-4 flex items-center justify-center text-sm font-bold transition-colors duration-300 shrink-0"
                           :class="currentConsultingStep === index ? 'bg-white text-indigo-600' : 'bg-indigo-500 text-white'">
                        {{ index + 1 }}
                      </div>
                      <span class="text-sm font-medium">{{ step }}</span>
                    </div>
                  </div>
                </div>
              </div>
              <div>
                <h3 class="text-4xl font-bold text-gray-900 mb-4">Consultoría</h3>
                <p class="text-gray-700 mb-6 leading-relaxed">Asesoría especializada para definir la mejor estrategia digital para tu empresa.</p>
                <ul class="space-y-3 mb-8">
                  <li class="flex items-center text-gray-700">
                    <span class="text-indigo-500 mr-3 text-lg">→</span>
                    Análisis integral del negocio
                  </li>
                  <li class="flex items-center text-gray-700">
                    <span class="text-indigo-500 mr-3 text-lg">→</span>
                    Estrategias personalizadas
                  </li>
                  <li class="flex items-center text-gray-700">
                    <span class="text-indigo-500 mr-3 text-lg">→</span>
                    Acompañamiento continuo
                  </li>
                </ul>
                <button class="bg-gradient-to-r from-indigo-500 to-purple-500 text-white px-8 py-4 rounded-xl font-semibold hover:from-indigo-600 hover:to-purple-600 transform hover:scale-105 transition-all duration-300 shadow-lg">
                  Empezar ahora
                </button>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </template>
  
  <script setup>
  import { ref, onMounted, onUnmounted } from 'vue'
  
  // Desarrollo Web Animation
  const codeLines = ref({
    line1: '<div class="hero-section">',
    line2: '<h1 class="title">',
    line3: 'Bienvenido a tu sitio',
    activeElement: '</h1>',
    line4: '<button class="cta">',
    line5: '</div>'
  })
  
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
  
  let intervals = []
  
  onMounted(() => {
    // Code Animation
    intervals.push(setInterval(() => {
      const elements = ['Bienvenido a tu sitio', 'Diseño moderno', 'Optimizado para SEO', 'Conversiones altas']
      const currentIndex = elements.indexOf(codeLines.value.line3)
      codeLines.value.line3 = elements[(currentIndex + 1) % elements.length]
    }, 3000))
  
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
  </style>