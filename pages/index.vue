<template>
  <div class="w-full h-[100dvh] flex flex-col bg-light text-dark bg-grid relative overflow-hidden">
    <Navbar />

    <!-- Animated Background Elements -->
    <div class="absolute inset-0 pointer-events-none overflow-hidden">
      <!-- Floating Orbs -->
      <div v-for="i in 8" :key="'orb-' + i"
           class="absolute rounded-full bg-gradient-to-br from-[#F97315]/20 to-[#F97315]/5 blur-xl"
           :class="getOrbSize(i)"
           :style="getOrbStyle(i)"></div>

    </div>

    <!-- Main Content -->
    <div class="flex-1 flex flex-col justify-center items-center text-center relative z-10 px-5 md:px-10">

      <!-- Hero Section -->
      <div class="max-w-6xl mx-auto">
        <!-- Main Title with Staggered Animation -->
        <div class="mb-8">
          <h1 class="text-6xl md:text-9xl font-black font-gambarino leading-none">
            <span class="inline-block title-char" style="animation-delay: 0.1s;">K</span>
            <span class="inline-block title-char" style="animation-delay: 0.2s;">a</span>
            <span class="inline-block title-char" style="animation-delay: 0.3s;">k</span>
            <span class="inline-block title-char" style="animation-delay: 0.4s;">t</span>
            <span class="inline-block title-char" style="animation-delay: 0.5s;">u</span>
            <span class="inline-block title-char" style="animation-delay: 0.6s;">s</span>
            <span class="inline-block title-char" style="animation-delay: 0.7s;">e</span>
            <span class="inline-block title-char text-[#F97315]" style="animation-delay: 0.8s;">.</span>
          </h1>
        </div>

        <!-- Dynamic Tagline -->
        <div class="mb-12">
          <h2 class="text-2xl md:text-4xl font-medium mb-4 fade-in-up" style="animation-delay: 1.2s;">
            Crafting
            <span class="relative inline-block mx-2">
              <span class="text-[#F97315] font-bold italic">{{ displayedWord }}</span>
              <span class="typing-cursor">|</span>
            </span>
            web experiences
          </h2>
          <p class="text-lg md:text-xl text-description max-w-2xl mx-auto fade-in-up" style="animation-delay: 1.4s;">
            Where innovation meets creativity in the digital realm
          </p>
        </div>

        <!-- Call to Action Buttons -->
        <div class="flex flex-col sm:flex-row gap-4 justify-center items-center fade-in-up" style="animation-delay: 1.6s;">
          <NuxtLink to="/portfolio"
                    class="cta-button primary group">
            <Icon name="solar:folder-bold-duotone" size="1.2em" />
            <span>View My Work</span>
            <Icon name="solar:arrow-right-bold" class="group-hover:translate-x-1 transition-transform" />
          </NuxtLink>

          <NuxtLink to="/contact"
                    class="cta-button secondary group">
            <Icon name="solar:letter-bold-duotone" size="1.2em" />
            <span>Start a Project</span>
            <Icon name="solar:link-bold" class="group-hover:scale-110 transition-transform" />
          </NuxtLink>
        </div>

        <!-- Quick Stats -->
        <div class="mt-16 grid grid-cols-3 gap-8 max-w-md mx-auto fade-in-up" style="animation-delay: 1.8s;">
          <div class="text-center">
            <div class="text-2xl md:text-3xl font-bold text-[#F97315] counter" data-target="50">0</div>
            <div class="text-sm text-description">Projects</div>
          </div>
          <div class="text-center">
            <div class="text-2xl md:text-3xl font-bold text-[#F97315] counter" data-target="3">0</div>
            <div class="text-sm text-description">Years</div>
          </div>
          <div class="text-center">
            <div class="text-2xl md:text-3xl font-bold text-[#F97315] counter" data-target="24">0</div>
            <div class="text-sm text-description">Response (h)</div>
          </div>
        </div>
      </div>
    </div>

    <!-- Scroll Indicator -->
    <div class="absolute bottom-8 left-1/2 transform -translate-x-1/2 scroll-indicator fade-in-up" style="animation-delay: 2s;">
      <div class="flex flex-col items-center text-description">
        <span class="text-sm mb-2">Explore</span>
        <div class="w-6 h-10 border-2 border-current rounded-full relative">
          <div class="w-1 h-3 bg-current rounded-full absolute top-2 left-1/2 transform -translate-x-1/2 scroll-dot"></div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue'

useHead({
  title: 'Kaktuse - Crafting impactful web solutions',
  meta: [
    { name: 'description', content: 'Kaktuse is a web development agency that crafts impactful web solutions for businesses and startups.' },
    { name: 'keywords', content: 'web development, web design, web solutions, web applications, startups, businesses' },
    { name: 'author', content: 'Yann Thevenin' },
    { property: 'og:title', content: 'Kaktuse - Crafting impactful web solutions' },
    { property: 'og:description', content: 'Kaktuse is a web development agency that crafts impactful web solutions for businesses and startups.' },
    { property: 'og:image', content: 'https://kaktuse.net/og.png' },
    { property: 'og:url', content: 'https://kaktuse.net' },
    { property: 'og:type', content: 'website' },
    { name: 'twitter:card', content: 'summary_large_image' },
    { name: 'twitter:title', content: 'Kaktuse - Crafting impactful web solutions' },
    { name: 'twitter:description', content: 'Kaktuse is a web development agency that crafts impactful web solutions for businesses and startups.' },
    { name: 'twitter:image', content: 'https://kaktuse.net/og.png' }
  ],
  link: [
    { rel: 'icon', type: 'image/x-icon', href: '/favicon.ico' }
  ]
})

const displayedWord = ref('')
const words = ['impactful', 'modern', 'scalable', 'innovative', 'beautiful']
let wordIndex = 0
let charIndex = 0
let isDeleting = false

function startTypewriter() {
  const currentWord = words[wordIndex]

  if (!isDeleting) {
    // Typing
    displayedWord.value = currentWord.slice(0, charIndex + 1)
    charIndex++

    if (charIndex === currentWord.length) {
      // Word complete, wait then start deleting
      setTimeout(() => {
        isDeleting = true
        typewriterStep()
      }, 2000)
      return
    }
  } else {
    // Deleting
    displayedWord.value = currentWord.slice(0, charIndex)
    charIndex--

    if (charIndex < 0) {
      // Deletion complete, move to next word
      isDeleting = false
      wordIndex = (wordIndex + 1) % words.length
      charIndex = 0
      setTimeout(typewriterStep, 500)
      return
    }
  }

  setTimeout(typewriterStep, isDeleting ? 50 : 100)
}

function typewriterStep() {
  startTypewriter()
}

onMounted(() => {
  // Start typewriter effect after initial animation
  setTimeout(startTypewriter, 2000)

  // Counter animations
  setTimeout(() => {
    const counters = document.querySelectorAll('.counter')
    counters.forEach(counter => {
      const target = parseInt(counter.dataset.target)
      let current = 0
      const increment = target / 60
      const timer = setInterval(() => {
        current += increment
        counter.textContent = Math.floor(current)
        if (current >= target) {
          counter.textContent = target
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
  // Pseudo-random positioning
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
/* Character Animation */
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

/* Fade in up animation */
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

/* CTA Buttons */
.cta-button {
  @apply inline-flex items-center gap-3 px-8 py-4 rounded-2xl font-medium transition-all duration-300 hover:shadow-lg hover:transform hover:-translate-y-1;
}

.cta-button.primary {
  @apply bg-[#F97315] text-white hover:bg-[#ea580c] hover:shadow-[#F97315]/25;
}

.cta-button.secondary {
  @apply bg-white border-2 border-gray-200 text-gray-900 hover:border-[#F97315] hover:text-[#F97315] hover:shadow-gray-200/50;
}

/* Typing Cursor */
.typing-cursor {
  animation: blink 1s infinite;
  color: #F97315;
}

@keyframes blink {
  0%, 50% { opacity: 1; }
  51%, 100% { opacity: 0; }
}

/* Floating Orbs */
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


/* Scroll Indicator */
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

/* Responsive adjustments */
@media (max-width: 768px) {
  .title-char {
    font-size: 4rem;
  }

  .cta-button {
    @apply px-6 py-3;
  }
}
</style>