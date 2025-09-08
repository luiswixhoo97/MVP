<script setup>
import { ref, onMounted, onBeforeUnmount, watch, computed } from 'vue'

const props = defineProps({
  text: { type: [String, Array], required: true },
  typingSpeed: { type: Number, default: 50 },
  initialDelay: { type: Number, default: 0 },
  pauseDuration: { type: Number, default: 2000 },
  deletingSpeed: { type: Number, default: 30 },
  loop: { type: Boolean, default: true },
  showCursor: { type: Boolean, default: true },
  hideCursorWhileTyping: { type: Boolean, default: false },
  cursorCharacter: { type: String, default: '|' },
  cursorBlinkDuration: { type: Number, default: 500 },
  textColors: { type: Array, default: () => [] },
  variableSpeed: { type: Object, default: null },
  startOnVisible: { type: Boolean, default: false },
  reverseMode: { type: Boolean, default: false }
})

const containerRef = ref(null)
const cursorRef = ref(null)
const displayedText = ref('')
const currentCharIndex = ref(0)
const isDeleting = ref(false)
const currentTextIndex = ref(0)
const isVisible = ref(!props.startOnVisible)
let intervalId = null

const textArray = computed(() => Array.isArray(props.text) ? props.text : [props.text])

const getRandomSpeed = () => {
  if (!props.variableSpeed) return props.typingSpeed
  const { min, max } = props.variableSpeed
  return Math.random() * (max - min) + min
}

const getCurrentTextColor = computed(() => {
  if (!props.textColors || props.textColors.length === 0) return undefined
  return props.textColors[currentTextIndex.value % props.textColors.length]
})

onMounted(() => {
  if (props.startOnVisible && containerRef.value) {
    const observer = new IntersectionObserver((entries) => {
      entries.forEach((entry) => {
        if (entry.isIntersecting) {
          isVisible.value = true
        }
      })
    }, { threshold: 0.1 })
    observer.observe(containerRef.value)
  }

  if (props.showCursor && cursorRef.value) {
    // Blink using CSS via inline style and keyframes below
  }
})

onBeforeUnmount(() => {
  if (intervalId) clearTimeout(intervalId)
})

const run = () => {
  if (!isVisible.value) return
  const currentText = textArray.value[currentTextIndex.value]
  const processedText = props.reverseMode ? currentText.split('').reverse().join('') : currentText

  if (isDeleting.value) {
    if (displayedText.value === '') {
      isDeleting.value = false
      if (currentTextIndex.value === textArray.value.length - 1 && !props.loop) return
      // Avanzar de frase si hay varias; si solo hay una, reiniciar la misma
      currentTextIndex.value = textArray.value.length > 1
        ? (currentTextIndex.value + 1) % textArray.value.length
        : 0
      currentCharIndex.value = 0
      intervalId = setTimeout(run, props.pauseDuration)
    } else {
      intervalId = setTimeout(() => {
        displayedText.value = displayedText.value.slice(0, -1)
        run()
      }, props.deletingSpeed)
    }
  } else {
    if (currentCharIndex.value < processedText.length) {
      intervalId = setTimeout(() => {
        displayedText.value += processedText[currentCharIndex.value]
        currentCharIndex.value += 1
        run()
      }, props.variableSpeed ? getRandomSpeed() : props.typingSpeed)
    } else if (props.loop) {
      intervalId = setTimeout(() => {
        isDeleting.value = true
        run()
      }, props.pauseDuration)
    }
  }
}

watch(() => [isVisible.value], () => {
  if (isVisible.value) {
    setTimeout(run, props.initialDelay)
  }
}, { immediate: true })
</script>

<template>
  <span ref="containerRef" class="inline-flex items-baseline whitespace-nowrap">
    <span class="text-type__content" :style="{ color: getCurrentTextColor }">{{ displayedText }}</span>
    <span
      v-if="showCursor"
      ref="cursorRef"
      class="text-type__cursor"
      :style="{ '--cursor-blink-duration': cursorBlinkDuration + 'ms' }"
      :class="{ 'text-type__cursor--hidden': hideCursorWhileTyping && (currentCharIndex < (textArray[currentTextIndex] || '').length || isDeleting) }"
    >{{ cursorCharacter }}</span>
  </span>
  
</template>

<style scoped>
.text-type__cursor {
  margin-left: 0.125rem;
  animation: cursor-blink var(--cursor-blink-duration, 500ms) ease-in-out infinite alternate;
}
.text-type__cursor--hidden { opacity: 0; }

@keyframes cursor-blink {
  from { opacity: 1; }
  to { opacity: 0; }
}
</style>


