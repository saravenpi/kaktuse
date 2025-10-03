<template>
  <div class="w-full min-h-screen bg-light bg-grid text-dark relative overflow-hidden">
    <Navbar />

    <!-- Animated Background Elements -->
    <div class="absolute inset-0 pointer-events-none overflow-hidden">
      <!-- Floating Orbs -->
      <div v-for="i in 6" :key="'orb-' + i"
           class="absolute rounded-full bg-gradient-to-br from-[#F97315]/10 to-[#F97315]/3 blur-2xl"
           :class="getOrbSize(i)"
           :style="getOrbStyle(i)"></div>
    </div>

    <main class="relative z-10 p-5 md:p-10 pb-32 md:pb-32 pt-20 md:pt-10">

      <!-- Hero Section -->
      <section class="max-w-7xl mx-auto mb-16">
        <div class="text-center mb-12">
          <div class="inline-flex items-center gap-3 bg-[#F97315]/10 rounded-full px-6 py-2 mb-6 fade-in-up">
            <Icon name="solar:folder-bold-duotone" class="text-[#F97315]" size="1.2em" />
            <span class="text-[#F97315] font-medium">Portfolio</span>
          </div>

          <h1 class="text-5xl md:text-7xl font-bold mb-6 font-gambarino text-dark fade-in-up" style="animation-delay: 0.2s;">
            Featured Projects
          </h1>

          <p class="text-xl md:text-2xl text-description max-w-3xl mx-auto leading-relaxed fade-in-up" style="animation-delay: 0.4s;">
            Discover the innovative solutions I've crafted for clients across different industries
          </p>
        </div>

        <!-- Stats -->
        <div class="flex justify-center gap-12 mb-16 fade-in-up" style="animation-delay: 0.6s;">
          <div class="text-center">
            <div class="text-3xl font-bold text-[#F97315] mb-1">{{ projects.length }}+</div>
            <div class="text-description">Projects</div>
          </div>
          <div class="text-center">
            <div class="text-3xl font-bold text-[#F97315] mb-1">5+</div>
            <div class="text-description">Technologies</div>
          </div>
          <div class="text-center">
            <div class="text-3xl font-bold text-[#F97315] mb-1">100%</div>
            <div class="text-description">Success Rate</div>
          </div>
        </div>
      </section>

      <!-- Projects Grid -->
      <section class="max-w-7xl mx-auto">
        <!-- Flexible centered grid -->
        <div class="projects-container">
          <div v-for="(project, index) in projects" :key="project.id"
            class="flex flex-col project-card p-6 rounded-xl shadow-lg justify-between gap-4 stagger-animation"
            :style="{ animationDelay: `${0.8 + (index * 0.15)}s` }">

            <!-- Keep your existing card content exactly as is -->
            <div>
              <Icon :name="project.icon" class="text-4xl text-center mb-3 text-description" />
              <h2 class="text-3xl font-semibold mb-2">{{ project.title }}</h2>
              <p class="text-xl text-description">{{ project.description }}</p>
            </div>
            <div class="mt-3">
              <h2 class="text-xl mb-3 text-description font-bold flex items-center gap-2">
                <Icon name="solar:code-square-bold-duotone" />
                Languages/Frameworks
              </h2>
              <div class="flex flex-wrap gap-3">
                <Badge v-for="tech in project.technologies" :key="tech">
                  {{ tech }}
                </Badge>
              </div>
            </div>
            <div class="mt-3">
              <h2 class="text-xl mb-3 text-description font-bold flex items-center gap-2">
                <Icon name="solar:link-bold-duotone" />
                Links
              </h2>
              <a :href="project.link" target="_blank"
                class="text-primary font-bold hover:underline flex items-center gap-2 group">
                <Icon name="solar:external-link-bold-duotone" class="group-hover:scale-110 transition-transform" />
                Visit Project
              </a>
            </div>
          </div>
        </div>

        <!-- Call to Action -->
        <div class="text-center mt-20 fade-in-up" style="animation-delay: 2s;">
          <div class="bg-dark rounded-3xl p-8 md:p-12 text-light relative overflow-hidden">
            <!-- Background Pattern -->
            <div class="absolute inset-0 opacity-15 overflow-hidden">
              <div v-for="i in 150" :key="i"
                   class="absolute bg-white rounded-full dot-rain"
                   :class="getRainDotSize(i)"
                   :style="getRainDotStyle(i)"></div>
            </div>

            <div class="relative z-10">
              <h2 class="text-3xl md:text-4xl font-bold mb-4 font-gambarino">Have a Project in Mind?</h2>
              <p class="text-lg md:text-xl opacity-90 mb-8 max-w-2xl mx-auto">
                Let's collaborate to bring your vision to life with modern, scalable solutions
              </p>

              <div class="flex flex-col sm:flex-row gap-4 justify-center">
                <NuxtLink to="/contact"
                          class="cta-button primary group">
                  <Icon name="solar:letter-bold-duotone" size="1.2em" />
                  <span>Start a Project</span>
                  <Icon name="solar:arrow-right-bold" class="group-hover:translate-x-1 transition-transform" />
                </NuxtLink>

                <NuxtLink to="/about"
                          class="cta-button secondary group">
                  <Icon name="solar:user-bold-duotone" size="1.2em" />
                  <span>Learn More</span>
                  <Icon name="solar:external-link-bold" class="group-hover:scale-110 transition-transform" />
                </NuxtLink>
              </div>
            </div>
          </div>
        </div>
      </section>
    </main>
  </div>
</template>

<script>
useHead({
  title: 'Kaktuse - Portfolio',
})

export default {
  data() {
    return {
      projects: [
        {
          id: 1,
          title: 'Disti.life',
          description: 'Disti.life is a comprehensive ERP solution tailored for distilleries, integrating advanced AI technologies to optimize production processes, manage inventory, and enhance decision-making through predictive analytics.',
          technologies: ['Vue.js', 'Node.js', 'AI', 'PostegreSQL', 'Docker'],
          icon: 'solar:bottle-bold-duotone',
          link: 'https://disti.life'
        },
        {
          id: 2,
          title: 'Solais Intranet',
          description: 'Solais is a robust intranet platform designed for a solar company, facilitating seamless internal communication, document management, and collaboration among teams, while providing tools for project tracking and resource allocation.',
          technologies: ['Angular', 'ExpressJS', 'MongoDB', 'Typescript'],
          icon: 'solar:sun-2-bold-duotone',
          link: 'https://solais.fr'
        },
        {
          id: 3,
          title: 'Marcel',
          description: 'Marcel is an innovative gamified organisation app that transforms task management into an engaging experience, encouraging productivity and teamwork through game-like elements and rewards, suitable for both personal and professional use.',
          technologies: ['Svelte', 'Pocketbase', 'Typescript', 'GoLang'],
          icon: 'solar:checklist-minimalistic-bold-duotone',
          link: 'https://marcel.my'
        },
        {
          id: 4,
          title: 'OffOn',
          description: 'OffOn is a dynamic e-commerce platform specialized in smartphone sales and repairs, combining a sleek, user-friendly interface with powerful inventory and service management tools to streamline operations and enhance the customer experience.',
          technologies: ['Vue', 'Nuxt', 'Directus', 'Typescript'],
          icon: 'solar:monitor-smartphone-bold-duotone',
          link: 'https://offon.store'
        },
        {
          id: 5,
          title: 'Brain.h',
          description: 'Brain.h is a lightweight C library designed for building and training neural networks, offering a straightforward API and efficient performance, making it an ideal choice for developers seeking simplicity and control in AI projects.',
          technologies: ['C'],
          icon: 'solar:database-bold-duotone',
          link: 'https://github.com/saravenpi/brain.h'
        }
      ]
    }
  },
  methods: {
    getOrbSize(index) {
      const sizes = ['w-32 h-32', 'w-48 h-48', 'w-24 h-24', 'w-40 h-40', 'w-28 h-28', 'w-36 h-36']
      return sizes[index % sizes.length]
    },
    getOrbStyle(index) {
      const x = ((index * 31) % 90) + 5
      const y = ((index * 17) % 80) + 10
      const delay = (index * 1.2) % 5
      const duration = 10 + (index % 6)

      return {
        left: `${x}%`,
        top: `${y}%`,
        animationDelay: `${delay}s`,
        animationDuration: `${duration}s`
      }
    },
    getDotStyle(index) {
      const x = ((index * 23) % 95) + 2
      const y = ((index * 17) % 85) + 5
      const delay = (index * 0.1) % 3

      return {
        left: `${x}%`,
        top: `${y}%`,
        animationDelay: `${delay}s`
      }
    },
    getRainDotSize(index) {
      const rand = (index * 0.618) % 1 // Use golden ratio for better distribution
      if (rand > 0.8) return 'w-3 h-3'
      if (rand > 0.6) return 'w-2 h-2'
      if (rand > 0.3) return 'w-1.5 h-1.5'
      return 'w-1 h-1'
    },
    getRainDotStyle(index) {
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
  }
}
</script>

<style scoped>
/* Keep your existing project card styles exactly as they are */
.project-card {
  transition: transform 0.3s, opacity 0.5s, box-shadow 0.3s;
  opacity: 0;
  background: #FFF;
  border: 2px solid #7D6666;
}

.project-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 20px 40px rgba(0, 0, 0, 0.1);
}

/* New animations */
.fade-in-up {
  animation: fadeInUp 0.8s ease-out forwards;
  opacity: 0;
  transform: translateY(30px);
}

.stagger-animation {
  animation: fadeInUp 0.8s ease-out forwards;
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
  @apply bg-white/10 border-2 border-white/20 text-white hover:border-white/40 hover:bg-white/20;
}

/* Floating Orbs */
.absolute.rounded-full {
  animation: float 15s ease-in-out infinite;
}

@keyframes float {
  0%, 100% {
    transform: translateY(0px) translateX(0px) rotate(0deg);
  }
  25% {
    transform: translateY(-30px) translateX(20px) rotate(90deg);
  }
  50% {
    transform: translateY(-15px) translateX(-15px) rotate(180deg);
  }
  75% {
    transform: translateY(-40px) translateX(10px) rotate(270deg);
  }
}

/* Flexible Centered Layout */
.projects-container {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 2rem;
  align-items: stretch;
}

.project-card {
  flex: 0 0 auto;
  width: 100%;
  max-width: 400px;
  min-width: 320px;
}

/* Responsive breakpoints */
@media (min-width: 640px) {
  .project-card {
    width: calc(50% - 1rem);
  }
}

@media (min-width: 1024px) {
  .project-card {
    width: calc(33.333% - 1.333rem);
  }
}

@media (min-width: 1280px) {
  .project-card {
    width: calc(33.333% - 1.333rem);
    max-width: 380px;
  }
}

/* Mobile optimization */
@media (max-width: 639px) {
  .projects-container {
    max-width: 500px;
    margin: 0 auto;
  }

  .project-card {
    width: 100%;
    max-width: none;
  }
}

/* Rain Animation */
.dot-rain {
  animation: dotRain infinite linear;
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
</style>