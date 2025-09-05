<template>
  <header class="fixed top-0 w-full bg-white/90 backdrop-blur-md z-50 border-b border-gray-100">
    <nav ref="navRef" class="container mx-auto px-6 h-[120px] lg:h-[140px] flex items-center">
      <div class="flex items-center justify-between w-full overflow-visible">
        <div class="flex items-center space-x-1 overflow-visible">
          <img ref="logoRef" src="/mvp_logo.svg" alt="MVP DIGITAL" class="h-[180px] lg:h-[228px] w-auto" />
        </div>

        <div class="hidden md:flex items-center space-x-12">
          <a href="#inicio" class="text-gray-700 font-bold text-lg  lg:text-xl xl:text-2xl hover:text-purple-600 transition-colors">Inicio</a>
          <a href="#servicios" class="text-gray-700 font-bold text-lg lg:text-xl xl:text-2xl hover:text-purple-600 transition-colors">Servicios</a>
          <a href="#nosotros" class="text-gray-700 font-bold text-lg lg:text-xl xl:text-2xl hover:text-purple-600 transition-colors">Nosotros</a>
          <a href="#contacto" class="text-gray-700 font-bold text-lg lg:text-xl xl:text-2xl hover:text-purple-600 transition-colors">Contacto</a>
        </div>

        <button class="bg-gradient-to-r from-purple-500 to-pink-500 text-white px-10 lg:px-12 py-4 lg:py-5 rounded-full text-lg lg:text-xl xl:text-2xl hover:shadow-lg transform hover:scale-105 transition-all duration-300">
          Cotizar Ahora
        </button>
      </div>
    </nav>
  </header>
</template>

<script setup>
import { onMounted, onBeforeUnmount, ref, nextTick } from 'vue'

const navRef = ref(null)
const logoRef = ref(null)

const setHeaderHeightVar = () => {
  const navEl = navRef.value
  const logoEl = logoRef.value
  if (!navEl) return
  const navHeight = navEl.offsetHeight
  const logoHeight = logoEl ? logoEl.offsetHeight : 0
  // Si el logo es más alto que el nav, usamos el mayor para despegar el hero
  const effectiveHeight = Math.max(navHeight, logoHeight)
  document.documentElement.style.setProperty('--header-height', `${effectiveHeight}px`)
}

const handleResize = () => setHeaderHeightVar()

onMounted(async () => {
  await nextTick()
  setHeaderHeightVar()
  window.addEventListener('resize', handleResize)
})

onBeforeUnmount(() => {
  window.removeEventListener('resize', handleResize)
})
</script>

<style scoped>
</style>


