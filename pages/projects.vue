<template>
  <div class="w-full h-full bg-[#161616] text-white">
    <Navbar />

    <main class="p-5 md:p-10">
      <h1 class="text-4xl font-bold mb-8">Our Projects</h1>

      <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 gap-8">
        <div v-for="(project, index) in projects" :key="project.id"
          class="project-card p-6 border border-gray-300 rounded-lg shadow-lg"
          :style="{ animationDelay: `${index * 0.2}s` }">
          <h2 class="text-3xl font-semibold mb-2">{{ project.title }}</h2>
          <p class="text-xl">{{ project.description }}</p>
          <div class="flex flex-wrap mt-4">
            <span v-for="tech in project.technologies" :key="tech"
              class="border border-gray-300 text-gray-300 text-sm font-medium mr-2 mb-2 px-3 py-1 rounded">
              {{ tech }}
            </span>
          </div>
        </div>
      </div>
    </main>
  </div>
</template>

<script>
export default {
  name: 'ProjectsPage',
  data() {
    return {
      projects: [
        { id: 1, title: 'Disti.life', description: 'Disti.life is a comprehensive ERP solution tailored for distilleries, integrating advanced AI technologies to optimize production processes, manage inventory, and enhance decision-making through predictive analytics.', technologies: ['Vue.js', 'Node.js', 'AI', 'PostegreSQL', 'Docker'] },
        { id: 2, title: 'Solais Intranet', description: 'Solais is a robust intranet platform designed for a solar company, facilitating seamless internal communication, document management, and collaboration among teams, while providing tools for project tracking and resource allocation.', technologies: ['Angular', 'ExpressJS', 'MongoDB', 'Typescript'] },
        { id: 3, title: 'Marcel', description: 'Marcel is an innovative gamified organisation app that transforms task management into an engaging experience, encouraging productivity and teamwork through game-like elements and rewards, suitable for both personal and professional use.', technologies: ['Svelte', 'Pocketbase', 'Typescript', 'GoLang'] },
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
