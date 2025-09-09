<template>
  <div class="fixed top-1/2 right-5 -translate-y-1/2 z-50 flex flex-col items-center gap-3">
    <a :href="waHref" target="_blank" rel="noopener" aria-label="Abrir WhatsApp" class="inline-flex items-center justify-center w-16 h-16 sm:w-20 sm:h-20 rounded-full shadow-xl bg-[#25D366] text-white hover:scale-105 active:scale-95 transition-transform duration-200 transform-gpu ring-1 ring-black/5">
      <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" class="w-10 h-10 sm:w-12 sm:h-12" aria-hidden="true">
        <path fill="currentColor" d="M.057 24l1.687-6.163a11.867 11.867 0 0 1-1.62-6.003C.122 5.356 5.478 0 12.057 0c3.182 0 6.167 1.24 8.413 3.488a11.823 11.823 0 0 1 3.492 8.413c-.003 6.579-5.36 11.935-11.94 11.935a11.9 11.9 0 0 1-6.003-1.616L.057 24zm6.597-3.807c1.742 1.03 3.768 1.577 5.845 1.577 5.997 0 10.875-4.873 10.877-10.867.003-5.996-4.868-10.868-10.865-10.869-5.995 0-10.868 4.872-10.868 10.868a10.8 10.8 0 0 0 1.597 5.74l-.999 3.648 3.413-.997zm11.387-5.464c-.074-.124-.272-.198-.57-.347-.297-.149-1.758-.868-2.029-.967-.272-.099-.47-.149-.669.149-.198.297-.767.967-.94 1.165-.173.198-.347.223-.644.074-.297-.149-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.297-.347.446-.521.149-.173.198-.297.297-.495.099-.198.05-.372-.025-.521-.075-.149-.669-1.611-.916-2.206-.242-.579-.487-.5-.669-.51l-.57-.01c-.198 0-.521.074-.793.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.095 3.2 5.076 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.872.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413z"/>
      </svg>
    </a>

    <a :href="igHref" target="_blank" rel="noopener" aria-label="Abrir Instagram" class="inline-flex items-center justify-center w-16 h-16 sm:w-20 sm:h-20 rounded-full shadow-xl bg-[conic-gradient(at_50%_50%,#f58529,#dd2a7b,#8134af,#515bd4,#f58529)] text-white hover:scale-105 active:scale-95 transition-transform duration-200 transform-gpu ring-1 ring-black/5">
      <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" class="w-9 h-9 sm:w-10 sm:h-10" aria-hidden="true">
        <path fill="currentColor" d="M7 2C4.243 2 2 4.243 2 7v10c0 2.757 2.243 5 5 5h10c2.757 0 5-2.243 5-5V7c0-2.757-2.243-5-5-5H7zm0 2h10c1.654 0 3 1.346 3 3v10c0 1.654-1.346 3-3 3H7c-1.654 0-3-1.346-3-3V7c0-1.654 1.346-3 3-3zm11 1a1 1 0 100 2 1 1 0 000-2zM12 7a5 5 0 100 10 5 5 0 000-10zm0 2a3 3 0 110 6 3 3 0 010-6z"/>
      </svg>
    </a>

    <a :href="mailHref" aria-label="Enviar correo" class="inline-flex items-center justify-center w-16 h-16 sm:w-20 sm:h-20 rounded-full shadow-xl bg-gray-900 text-white hover:scale-105 active:scale-95 transition-transform duration-200 transform-gpu ring-1 ring-black/5">
      <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" class="w-9 h-9 sm:w-10 sm:h-10" aria-hidden="true">
        <path fill="currentColor" d="M20 4H4a2 2 0 00-2 2v12a2 2 0 002 2h16a2 2 0 002-2V6a2 2 0 00-2-2zm0 2v.01L12 12 4 6.01V6h16zM4 18V8l8 6 8-6v10H4z"/>
      </svg>
    </a>
  </div>
</template>

<script setup>
import { computed } from 'vue'

const phone = '523312345678'
const email = 'mvpdigital.gdl@gmail.com'
const instagram = 'https://instagram.com/' // reemplazar con tu perfil

const defaultMessage = 'Hola, me gustaría más información.'
const waHref = computed(() => `https://wa.me/${phone}?text=${encodeURIComponent(defaultMessage)}`)
const igHref = computed(() => instagram)
const mailHref = computed(() => `mailto:${email}?subject=${encodeURIComponent('Información')}%20&body=${encodeURIComponent(defaultMessage)}`)
</script>

<style scoped>
</style>


