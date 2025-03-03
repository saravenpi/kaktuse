<template>
  <div>
    <div class="w-full h-screen bg-light bg-grid text-dark overflow-y-auto">
      <Navbar />

      <main class="p-5 md:p-10">
        <h1 class="text-4xl font-bold mb-8 font-gambarino">Last Projects</h1>

        <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 gap-8">
          <div v-for="(project, index) in projects" :key="project.id"
            class="flex flex-col project-card p-6 rounded-xl shadow-lg justify-between gap-4"
            :style="{ animationDelay: `${index * 0.2}s` }">
            <div>
              <Icon :name="project.icon" class="text-4xl text-center mb-3 text-description" />
              <h2 class="text-3xl font-semibold mb-2">{{ project.title }}</h2>
              <p class="text-xl text-description">{{ project.description }}</p>
            </div>
            <div class="mt-3 ">
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
                class="text-primary font-bold hover:underline flex items-center gap-2">
                <Icon name="solar:external-link-bold-duotone" />
                Visit Project
              </a>
            </div>
          </div>
        </div>
      </main>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ProjectsPage',
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
  }
}
</script>

<style scoped>
.project-card {
  transition: transform 0.3s, opacity 0.5s;
  opacity: 0;
  animation: fadeIn 1s forwards;
  background: #FFF;
  border: 2px solid #7D6666;
}

@keyframes fadeIn {
  from {
    opacity: 0;
  }

  to {
    opacity: 1;
  }
}

.project-card:hover {
  transform: translateY(-5px);
}
</style>
