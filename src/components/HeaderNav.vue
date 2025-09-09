<template>
  <header class="fixed top-0 w-full bg-white/90 backdrop-blur-md z-50 border-b border-gray-100">
    <nav ref="navRef" class="container mx-auto px-4 py-0 flex items-center">
      <div class="flex items-center justify-between w-full overflow-visible">
        <div class="flex items-center space-x-1 overflow-visible">
          <img ref="logoRef" src="/mvp_logo.svg" alt="MVP DIGITAL" class="h-20 sm:h-24 lg:h-28 xl:h-32 w-auto" />
        </div>

        <div class="hidden md:flex items-center space-x-8">
          <a href="#inicio" class="text-gray-700 font-bold hover:text-purple-600 transition-colors text-sm sm:text-base md:text-lg">Inicio</a>
          <a href="#servicios" class="text-gray-700 font-bold hover:text-purple-600 transition-colors text-sm sm:text-base md:text-lg">Servicios</a>
          <a href="#nosotros" class="text-gray-700 font-bold hover:text-purple-600 transition-colors text-sm sm:text-base md:text-lg">Nosotros</a>
          <a href="#contacto" class="text-gray-700 font-bold hover:text-purple-600 transition-colors text-sm sm:text-base md:text-lg">Contacto</a>
        </div>

        <div class="flex items-center gap-3">
          <button class="bg-gradient-to-r from-purple-500 to-pink-500 text-white px-9 py-3 md:px-10 md:py-4 rounded-full text-base md:text-lg hover:shadow-lg transform hover:scale-105 transition-all duration-300 hidden md:inline-block">
            Cotizar Ahora
          </button>
          <button @click="isMobileOpen = !isMobileOpen" class="md:hidden inline-flex items-center justify-center w-12 h-12 rounded-lg border border-gray-200 text-gray-700">
            <span v-if="!isMobileOpen">☰</span>
            <span v-else>✕</span>
          </button>
        </div>
      </div>
      <div v-if="isMobileOpen" class="md:hidden absolute left-0 right-0 top-full bg-white border-b border-gray-100 shadow">
        <div class="container mx-auto px-6 py-4 flex flex-col gap-2">
          <a href="#inicio" @click="isMobileOpen=false" class="py-3 text-gray-700 hover:text-purple-600 text-lg font-semibold">Inicio</a>
          <a href="#servicios" @click="isMobileOpen=false" class="py-3 text-gray-700 hover:text-purple-600 text-lg font-semibold">Servicios</a>
          <a href="#nosotros" @click="isMobileOpen=false" class="py-3 text-gray-700 hover:text-purple-600 text-lg font-semibold">Nosotros</a>
          <a href="#contacto" @click="isMobileOpen=false" class="py-3 text-gray-700 hover:text-purple-600 text-lg font-semibold">Contacto</a>
          <button class="mt-2 bg-gradient-to-r from-purple-500 to-pink-500 text-white px-6 py-4 rounded-lg text-lg font-semibold">Cotizar Ahora</button>
        </div>
      </div>
    </nav>
  </header>
</template>

<script setup>
import { onMounted, onBeforeUnmount, ref, nextTick } from 'vue'

const navRef = ref(null)
const logoRef = ref(null)

const isMobileOpen = ref(false)

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


