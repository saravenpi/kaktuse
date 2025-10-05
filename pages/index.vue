<template>
  <div class="w-full h-[100dvh] flex flex-col bg-light text-dark bg-grid relative overflow-hidden">
    <Navbar />

    <div class="absolute inset-0 pointer-events-none overflow-hidden">
      <div v-for="i in 8" :key="'orb-' + i"
           class="absolute rounded-full bg-gradient-to-br from-[#F97315]/20 to-[#F97315]/5 blur-xl"
           :class="getOrbSize(i)"
           :style="getOrbStyle(i)"></div>

    </div>

    <div class="flex-1 flex flex-col justify-center items-center text-center relative z-10 px-5 md:px-10 pt-16 pb-32 md:pb-28">

      <div class="max-w-6xl mx-auto">
        <div class="mb-8">
          <h1 class="text-6xl md:text-9xl font-black font-gambarino leading-none">
            <span class="inline-block title-char" style="animation-delay: 0.1s;">{{ $t('home.title').charAt(0) }}</span>
            <span class="inline-block title-char" style="animation-delay: 0.2s;">{{ $t('home.title').charAt(1) }}</span>
            <span class="inline-block title-char" style="animation-delay: 0.3s;">{{ $t('home.title').charAt(2) }}</span>
            <span class="inline-block title-char" style="animation-delay: 0.4s;">{{ $t('home.title').charAt(3) }}</span>
            <span class="inline-block title-char" style="animation-delay: 0.5s;">{{ $t('home.title').charAt(4) }}</span>
            <span class="inline-block title-char" style="animation-delay: 0.6s;">{{ $t('home.title').charAt(5) }}</span>
            <span class="inline-block title-char" style="animation-delay: 0.7s;">{{ $t('home.title').charAt(6) }}</span>
            <span class="inline-block title-char text-[#F97315]" style="animation-delay: 0.8s;">{{ $t('home.title').charAt(7) }}</span>
          </h1>
        </div>

        <div class="mb-12">
          <div class="text-2xl md:text-4xl font-medium mb-4 fade-in-up" style="animation-delay: 1.2s;">
            <div class="mb-2">
              {{ $t('home.subtitle') }}
            </div>
            <div class="text-[#F97315] font-bold italic">
              {{ displayedWord }}<span class="typing-cursor">|</span>
            </div>
          </div>
          <p class="text-lg md:text-xl text-description max-w-2xl mx-auto fade-in-up" style="animation-delay: 1.4s;">
            {{ $t('home.tagline') }}
          </p>
        </div>

        <div class="flex flex-col sm:flex-row gap-4 justify-center items-center fade-in-up" style="animation-delay: 1.6s;">
          <NuxtLink to="/portfolio"
                    class="cta-button primary group">
            <Icon name="solar:folder-bold-duotone" size="1.2em" />
            <span>{{ $t('home.cta.view_work') }}</span>
            <Icon name="solar:arrow-right-bold" class="group-hover:translate-x-1 transition-transform" />
          </NuxtLink>

          <NuxtLink to="/contact"
                    class="cta-button secondary group">
            <Icon name="solar:letter-bold-duotone" size="1.2em" />
            <span>{{ $t('home.cta.start_project') }}</span>
            <Icon name="solar:link-bold" class="group-hover:scale-110 transition-transform" />
          </NuxtLink>
        </div>

        <div class="mt-16 mb-8 grid grid-cols-3 gap-8 max-w-md mx-auto fade-in-up" style="animation-delay: 1.8s;">
          <div class="text-center">
            <div class="text-2xl md:text-3xl font-bold text-[#F97315] counter" data-target="47" data-show-plus="true">0</div>
            <div class="text-sm text-description">{{ $t('home.stats.projects') }}</div>
          </div>
          <div class="text-center">
            <div class="text-2xl md:text-3xl font-bold text-[#F97315] counter" data-target="3">0</div>
            <div class="text-sm text-description">{{ $t('home.stats.years') }}</div>
          </div>
          <div class="text-center">
            <div class="text-2xl md:text-3xl font-bold text-[#F97315] counter" data-target="24">0</div>
            <div class="text-sm text-description">{{ $t('home.stats.response_time') }}</div>
          </div>
        </div>
      </div>
    </div>

  </div>
</template>

<script setup>
import { ref, onMounted, watch, computed } from 'vue'
const { t, locale } = useI18n()

useHead({
  title: t('meta.home.title'),
  meta: [
    { name: 'description', content: t('meta.home.description') },
    { name: 'keywords', content: 'web development, web design, web solutions, web applications, startups, businesses' },
    { name: 'author', content: 'Yann Thevenin' },
    { property: 'og:title', content: t('meta.home.title') },
    { property: 'og:description', content: t('meta.home.description') },
    { property: 'og:image', content: 'https://kaktuse.net/og.png' },
    { property: 'og:url', content: 'https://kaktuse.net' },
    { property: 'og:type', content: 'website' },
    { name: 'twitter:card', content: 'summary_large_image' },
    { name: 'twitter:title', content: t('meta.home.title') },
    { name: 'twitter:description', content: t('meta.home.description') },
    { name: 'twitter:image', content: 'https://kaktuse.net/og.png' }
  ],
  link: [
    { rel: 'icon', type: 'image/x-icon', href: '/favicon.ico' }
  ]
})

const displayedWord = ref(t('home.typewriter.impactful'))
const words = computed(() => [
  t('home.typewriter.impactful'),
  t('home.typewriter.modern'),
  t('home.typewriter.scalable'),
  t('home.typewriter.innovative'),
  t('home.typewriter.beautiful')
])

let wordIndex = 0
let charIndex = t('home.typewriter.impactful').length
let isDeleting = false
let typewriterTimer = null

function startTypewriter() {
  const currentWord = words.value[wordIndex]

  if (!isDeleting) {
    displayedWord.value = currentWord.slice(0, charIndex + 1)
    charIndex++

    if (charIndex === currentWord.length) {
      typewriterTimer = setTimeout(() => {
        isDeleting = true
        typewriterStep()
      }, 2000)
      return
    }
  } else {
    displayedWord.value = currentWord.slice(0, charIndex)
    charIndex--

    if (charIndex < 0) {
      isDeleting = false
      wordIndex = (wordIndex + 1) % words.value.length
      charIndex = 0
      typewriterTimer = setTimeout(typewriterStep, 500)
      return
    }
  }

  typewriterTimer = setTimeout(typewriterStep, isDeleting ? 50 : 100)
}

function startInitialAnimation() {
  typewriterTimer = setTimeout(() => {
    isDeleting = true
    typewriterStep()
  }, 2000)
}

function typewriterStep() {
  startTypewriter()
}

function resetTypewriter() {
  if (typewriterTimer) {
    clearTimeout(typewriterTimer)
    typewriterTimer = null
  }
  wordIndex = 0
  charIndex = words.value[0].length
  isDeleting = false
  displayedWord.value = words.value[0]
  startInitialAnimation()
}

watch(locale, () => {
  resetTypewriter()
})

onMounted(() => {
  setTimeout(startInitialAnimation, 2000)

  setTimeout(() => {
    const counters = document.querySelectorAll('.counter')
    counters.forEach(counter => {
      const target = parseInt(counter.dataset.target)
      const showPlus = counter.dataset.showPlus === 'true'
      let current = 0
      const increment = target / 60
      const timer = setInterval(() => {
        current += increment
        counter.textContent = Math.floor(current)
        if (current >= target) {
          counter.textContent = showPlus ? target + '+' : target
          clearInterval(timer)
        }
      }, 30)
    })
  }, 2000)
})

function getOrbSize(index) {
  const sizes = ['w-32 h-32', 'w-48 h-48', 'w-24 h-24', 'w-40 h-40', 'w-20 h-20', 'w-36 h-36', 'w-28 h-28', 'w-44 h-44']
  return sizes[index % sizes.length]
}

function getOrbStyle(index) {
  const x = ((index * 23) % 85) + 5
  const y = ((index * 17) % 70) + 10
  const delay = (index * 0.8) % 4
  const duration = 8 + (index % 4)

  return {
    left: `${x}%`,
    top: `${y}%`,
    animationDelay: `${delay}s`,
    animationDuration: `${duration}s`
  }
}
</script>

<style scoped>
.title-char {
  animation: bounceInDown 0.8s cubic-bezier(0.68, -0.55, 0.265, 1.55) forwards;
  opacity: 0;
  transform: translateY(-100px);
}

@keyframes bounceInDown {
  0% {
    opacity: 0;
    transform: translateY(-100px);
  }
  60% {
    opacity: 1;
    transform: translateY(10px);
  }
  80% {
    transform: translateY(-5px);
  }
  100% {
    opacity: 1;
    transform: translateY(0);
  }
}

.fade-in-up {
  animation: fadeInUp 0.8s ease-out forwards;
  opacity: 0;
  transform: translateY(30px);
}

@keyframes fadeInUp {
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.cta-button {
  @apply inline-flex items-center gap-3 px-8 py-4 rounded-2xl font-medium transition-all duration-300 hover:shadow-lg hover:transform hover:-translate-y-1;
}

.cta-button.primary {
  @apply bg-[#F97315] text-white hover:bg-[#ea580c] hover:shadow-[#F97315]/25;
}

.cta-button.secondary {
  @apply bg-white border-2 border-gray-200 text-gray-900 hover:border-[#F97315] hover:text-[#F97315] hover:shadow-gray-200/50;
}

.typing-cursor {
  animation: blink 1s infinite;
  color: #F97315;
}

@keyframes blink {
  0%, 50% { opacity: 1; }
  51%, 100% { opacity: 0; }
}

.absolute.rounded-full {
  animation: float 12s ease-in-out infinite;
}

@keyframes float {
  0%, 100% {
    transform: translateY(0px) translateX(0px) rotate(0deg);
  }
  25% {
    transform: translateY(-20px) translateX(10px) rotate(90deg);
  }
  50% {
    transform: translateY(-10px) translateX(-10px) rotate(180deg);
  }
  75% {
    transform: translateY(-30px) translateX(5px) rotate(270deg);
  }
}


.scroll-dot {
  animation: scrollBounce 2s infinite;
}

@keyframes scrollBounce {
  0%, 100% {
    transform: translateX(-50%) translateY(0);
  }
  50% {
    transform: translateX(-50%) translateY(12px);
  }
}

@media (max-width: 768px) {
  .title-char {
    font-size: 4rem;
  }

  .cta-button {
    @apply px-6 py-3;
  }

}
</style>