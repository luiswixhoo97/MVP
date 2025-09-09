<template>
  <section id="valores" class="py-20">
    <div class="container mx-auto px-6">
      <div class="text-center mb-14">
        <h2 class="text-5xl lg:text-6xl font-extrabold mb-4">
          <span class="bg-gradient-to-r from-purple-600 via-pink-600 to-orange-500 bg-clip-text text-transparent">Nuestros Valores</span>
        </h2>
        <p class="text-gray-700 text-lg max-w-3xl mx-auto">
          Los principios que guían cada proyecto y relación con nuestros clientes, construyendo
          confianza y resultados excepcionales
        </p>
      </div>

      <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8">
        <div v-for="(v,i) in values" :key="i" class="bg-white rounded-2xl shadow-xl p-6">
          <div class="flex items-center gap-4 mb-4">
            <div class="w-12 h-12 rounded-xl bg-gradient-to-r from-pink-500 to-purple-500 flex items-center justify-center text-white text-xl">
              <span>{{ v.icon }}</span>
            </div>
            <h3 class="text-xl font-extrabold text-gray-900">{{ v.title }}</h3>
          </div>
          <p class="text-gray-700 leading-relaxed text-sm">{{ v.description }}</p>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue'

const values = ref([
  { icon: '🤝', title: 'Cercanía', description: 'Promovemos colaboraciones reales y relevantes que conectan genuinamente con las audiencias.' },
  { icon: '💡', title: 'Innovación', description: 'Nos mantenemos a la vanguardia del marketing digital para ofrecer campañas creativas y efectivas.' },
  { icon: '📈', title: 'Resultados', description: 'Nos enfocamos en KPIs claros de distribución, engagement y recordación.' },
  { icon: '🤜🤛', title: 'Colaboración', description: 'Trabajamos de la mano con marcas, medios e influencers como socios estratégicos.' },
  { icon: '🔄', title: 'Adaptabilidad', description: 'Evolucionamos con el entorno digital para mantenernos relevantes.' },
  { icon: '🏆', title: 'Excelencia', description: 'Cada campaña es una oportunidad para superar expectativas y elevar los estándares.' }
])
</script>

<style scoped>
</style>


