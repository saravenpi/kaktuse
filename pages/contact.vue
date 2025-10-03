<template>
  <div class="w-full min-h-screen bg-light bg-grid text-dark">
    <Navbar />

    <main class="p-5 md:p-10 pb-32 md:pb-32 pt-20 md:pt-10">
      <!-- Hero Section -->
      <section class="max-w-6xl mx-auto mb-16">
        <div class="text-center mb-12">
          <div class="inline-flex items-center gap-3 bg-[#F97315]/10 rounded-full px-6 py-2 mb-6 fade-in-up">
            <Icon name="solar:letter-bold-duotone" class="text-[#F97315]" size="1.2em" />
            <span class="text-[#F97315] font-medium">Contact</span>
          </div>

          <h1 class="text-5xl md:text-7xl font-bold mb-6 font-gambarino text-dark fade-in-up" style="animation-delay: 0.2s;">Let's Connect</h1>
          <p class="text-xl md:text-2xl text-description max-w-4xl mx-auto leading-relaxed fade-in-up" style="animation-delay: 0.4s;">
            Ready to bring your ideas to life? Choose your preferred way to reach out
          </p>
        </div>
      </section>

      <!-- Contact Methods Grid -->
      <section class="max-w-6xl mx-auto mb-20">
        <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8">

          <!-- Email Card -->
          <div class="contact-card group cursor-pointer" @click="openEmail">
            <div class="contact-card-inner">
              <div class="flex flex-col items-center text-center">
                <div class="icon-container mb-6">
                  <Icon name="mdi:email-outline" size="3em" class="text-[#F97315]" />
                </div>
                <h3 class="text-2xl font-bold mb-3 font-gambarino">Email</h3>
                <p class="text-description mb-4">Send me a direct message</p>
                <div class="email-address">
                  <span class="text-[#F97315] font-medium">contact@kaktuse.net</span>
                </div>
                <div class="mt-4 flex items-center text-sm text-description">
                  <Icon name="mdi:clock-outline" class="mr-2" />
                  Usually responds within 24h
                </div>
              </div>
            </div>
          </div>

          <!-- LinkedIn Card -->
          <div class="contact-card group cursor-pointer" @click="openLinkedIn">
            <div class="contact-card-inner">
              <div class="flex flex-col items-center text-center">
                <div class="icon-container mb-6">
                  <Icon name="mdi:linkedin" size="3em" class="text-blue-600" />
                </div>
                <h3 class="text-2xl font-bold mb-3 font-gambarino">LinkedIn</h3>
                <p class="text-description mb-4">Connect professionally</p>
                <div class="linkedin-handle">
                  <span class="text-blue-600 font-medium">@thevyann</span>
                </div>
                <div class="mt-4 flex items-center text-sm text-description">
                  <Icon name="mdi:account-network" class="mr-2" />
                  Professional networking
                </div>
              </div>
            </div>
          </div>

          <!-- GitHub Card -->
          <div class="contact-card group cursor-pointer" @click="openGitHub">
            <div class="contact-card-inner">
              <div class="flex flex-col items-center text-center">
                <div class="icon-container mb-6">
                  <Icon name="mdi:github" size="3em" class="text-gray-800" />
                </div>
                <h3 class="text-2xl font-bold mb-3 font-gambarino">GitHub</h3>
                <p class="text-description mb-4">Check out my work</p>
                <div class="github-handle">
                  <span class="text-gray-800 font-medium">@saravenpi</span>
                </div>
                <div class="mt-4 flex items-center text-sm text-description">
                  <Icon name="mdi:code-braces" class="mr-2" />
                  Open source projects
                </div>
              </div>
            </div>
          </div>

        </div>
      </section>

      <!-- Quick Contact Section -->
      <section class="max-w-4xl mx-auto">
        <div class="bg-dark rounded-3xl p-8 md:p-12 text-light relative overflow-hidden">
          <!-- Background Pattern -->
          <div class="absolute inset-0 opacity-15 overflow-hidden">
            <div v-for="i in 150" :key="i"
                 class="absolute bg-white rounded-full"
                 :class="[getDotSize(i), getDotAnimation(i)]"
                 :style="getDotStyle(i)"></div>
          </div>

          <div class="relative z-10">
            <div class="text-center mb-8">
              <h2 class="text-3xl md:text-4xl font-bold mb-4 font-gambarino">Ready to Start?</h2>
              <p class="text-lg md:text-xl opacity-90 mb-8">
                Got a project in mind? Let's discuss how we can bring it to life together.
              </p>
            </div>

            <div class="grid md:grid-cols-2 gap-6">
              <!-- Quick Email Button -->
              <button @click="openQuickEmail"
                      class="quick-action-btn bg-[#F97315] hover:bg-[#ea580c] text-white">
                <Icon name="mdi:rocket-launch" size="1.5em" />
                <span>Start a Project</span>
                <Icon name="mdi:arrow-right" />
              </button>

              <!-- Schedule Call Button -->
              <button @click="scheduleCall"
                      class="quick-action-btn bg-white/10 hover:bg-white/20 text-white border border-white/20">
                <Icon name="mdi:calendar-clock" size="1.5em" />
                <span>Schedule a Call</span>
                <Icon name="mdi:external-link" />
              </button>
            </div>

            <!-- Response Time -->
            <div class="mt-8 text-center">
              <div class="inline-flex items-center bg-white/10 rounded-full px-4 py-2">
                <div class="relative mr-2">
                  <!-- Center dot (always visible) -->
                  <div class="w-2 h-2 bg-green-400 rounded-full relative z-10"></div>
                  <!-- Animated halos -->
                  <div class="absolute inset-0 w-2 h-2 bg-green-400 rounded-full animate-ping opacity-75"></div>
                  <div class="absolute inset-0 w-2 h-2 bg-green-300 rounded-full halo-pulse"></div>
                </div>
                <span class="text-sm">Usually online • Quick responses</span>
              </div>
            </div>
          </div>
        </div>
      </section>

      <!-- FAQ Section -->
      <section class="max-w-4xl mx-auto mt-20">
        <div class="text-center mb-12">
          <h2 class="text-3xl md:text-4xl font-bold mb-4 font-gambarino text-dark">Quick Answers</h2>
          <p class="text-lg text-description">Common questions about working together</p>
        </div>

        <div class="space-y-4">
          <div v-for="(faq, index) in faqs" :key="index"
               class="faq-item bg-white rounded-2xl border border-gray-200 overflow-hidden">
            <button @click="toggleFaq(index)"
                    class="w-full p-6 text-left flex justify-between items-center hover:bg-gray-50 transition-colors">
              <span class="font-medium text-lg">{{ faq.question }}</span>
              <Icon name="mdi:chevron-down"
                    :class="['transition-transform', openFaq === index ? 'rotate-180' : '']" />
            </button>
            <transition name="faq-unfold">
              <div v-if="openFaq === index" class="faq-content">
                <div class="px-8 py-6">
                  <p class="text-description leading-relaxed">{{ faq.answer }}</p>
                </div>
              </div>
            </transition>
          </div>
        </div>
      </section>

    </main>
  </div>
</template>

<script setup>
import { ref } from 'vue'

useHead({
  title: 'Kaktuse - Contact',
})

const openFaq = ref(null)

const faqs = [
  {
    question: "What's your typical project timeline?",
    answer: "Most projects take 3-8 weeks depending on complexity. I'll provide a detailed timeline during our initial discussion."
  },
  {
    question: "Do you work with international clients?",
    answer: "Absolutely! I work with clients worldwide and am comfortable with different time zones and communication styles."
  },
  {
    question: "What technologies do you specialize in?",
    answer: "I specialize in Vue.js, Nuxt, TypeScript, SvelteKit, Golang, and Tailwind CSS for modern, scalable web applications."
  },
  {
    question: "How do you handle project pricing?",
    answer: "I provide custom quotes based on project scope, timeline, and requirements. Let's discuss your needs for an accurate estimate."
  }
]

function toggleFaq(index) {
  openFaq.value = openFaq.value === index ? null : index
}

function openEmail() {
  window.location.href = 'mailto:contact@kaktuse.net?subject=New Project Inquiry'
}

function openLinkedIn() {
  window.open('https://linkedin.com/in/thevyann', '_blank')
}

function openGitHub() {
  window.open('https://github.com/saravenpi', '_blank')
}

function openQuickEmail() {
  const subject = encodeURIComponent('Let\'s Start a Project Together!')
  const body = encodeURIComponent('Hi Yann,\n\nI\'d like to discuss a project with you.\n\nProject type: \nTimeline: \nBudget range: \n\nLooking forward to hearing from you!\n\nBest regards,')
  window.location.href = `mailto:contact@kaktuse.net?subject=${subject}&body=${body}`
}

function scheduleCall() {
  // This could be integrated with Calendly or similar
  window.open('mailto:contact@kaktuse.net?subject=Schedule a Call&body=Hi Yann,%0A%0AI\'d like to schedule a call to discuss my project.%0A%0APreferred time:%0AProject details:%0A%0AThanks!', '_blank')
}

function getDotSize(index) {
  const rand = (index * 0.618) % 1 // Use golden ratio for better distribution
  if (rand > 0.8) return 'w-3 h-3'
  if (rand > 0.6) return 'w-2 h-2'
  if (rand > 0.3) return 'w-1.5 h-1.5'
  return 'w-1 h-1'
}

function getDotAnimation(index) {
  // All dots will use the falling rain animation
  return 'dot-rain'
}

function getDotStyle(index) {
  // Use index-based pseudo-random generation for consistent positioning
  const x = ((index * 17) % 97) // Prime numbers for better distribution
  const startY = -10 - ((index * 19) % 30) // Start above the container
  const delay = ((index * 0.2) % 8) // Stagger the rain drops
  const duration = 3 + (((index * 13) % 20) * 0.2) // Rain fall duration
  const opacity = 0.4 + (((index * 11) % 40) * 0.01)

  return {
    left: `${x}%`,
    top: `${startY}%`,
    animationDelay: `${delay}s`,
    animationDuration: `${duration}s`,
    opacity: opacity
  }
}
</script>

<style scoped>
/* Contact Cards */
.contact-card {
  @apply bg-white rounded-2xl border-2 border-gray-100 p-6 transition-all duration-300 hover:shadow-lg hover:border-gray-200;
}

.contact-card:hover {
  @apply transform -translate-y-2;
}

.contact-card-inner {
  @apply h-full;
}

.icon-container {
  @apply w-20 h-20 rounded-full bg-gray-50 flex items-center justify-center group-hover:bg-gray-100 transition-colors;
}

/* Quick Action Buttons */
.quick-action-btn {
  @apply flex items-center justify-center gap-3 p-4 rounded-xl font-medium transition-all duration-200 hover:transform hover:scale-105;
}

/* FAQ Items */
.faq-item {
  @apply transition-all duration-300;
}

.faq-item:hover {
  @apply shadow-md;
}

.faq-content {
  @apply border-t border-gray-100;
}

/* FAQ Unfold Animation */
.faq-unfold-enter-active {
  transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
  transform-origin: top;
}

.faq-unfold-leave-active {
  transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
  transform-origin: top;
}

.faq-unfold-enter-from {
  opacity: 0;
  transform: scaleY(0) translateY(-10px);
  max-height: 0;
}

.faq-unfold-enter-to {
  opacity: 1;
  transform: scaleY(1) translateY(0);
  max-height: 200px;
}

.faq-unfold-leave-from {
  opacity: 1;
  transform: scaleY(1) translateY(0);
  max-height: 200px;
}

.faq-unfold-leave-to {
  opacity: 0;
  transform: scaleY(0) translateY(-10px);
  max-height: 0;
}

/* Animations */
@keyframes float {
  0%, 100% { transform: translateY(0px); }
  50% { transform: translateY(-10px); }
}

.contact-card:nth-child(1) {
  animation: float 6s ease-in-out infinite;
}

.contact-card:nth-child(2) {
  animation: float 6s ease-in-out infinite 2s;
}

.contact-card:nth-child(3) {
  animation: float 6s ease-in-out infinite 4s;
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

/* Dot Animations */
.dot-rain {
  animation: dotRain infinite linear;
}

/* Status Indicator */
.halo-pulse {
  animation: haloPulse 2s infinite ease-in-out;
}

@keyframes dotRain {
  0% {
    transform: translateY(0px);
    opacity: 0;
  }
  10% {
    opacity: 1;
  }
  90% {
    opacity: 1;
  }
  100% {
    transform: translateY(120vh);
    opacity: 0;
  }
}

@keyframes haloPulse {
  0% {
    transform: scale(1);
    opacity: 0.8;
  }
  50% {
    transform: scale(2.5);
    opacity: 0.2;
  }
  100% {
    transform: scale(1);
    opacity: 0.8;
  }
}
</style>