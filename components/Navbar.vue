<template>
  <!-- Desktop macOS Dock Style Navigation -->
  <div class="fixed bottom-6 left-1/2 transform -translate-x-1/2 z-50 hidden md:block">
    <div class="bg-white/10 backdrop-blur-lg rounded-3xl p-2 shadow-2xl border border-white/20">
      <div class="flex items-center space-x-2">
        <!-- Home -->
        <router-link
          to="/"
          class="dock-item group relative"
          :class="$route.path === '/' ? 'active' : ''"
        >
          <div class="icon-container">
            <Icon name="solar:home-bold-duotone" size="2em" :class="$route.path === '/' ? 'text-[#F97315]' : 'text-gray-700 group-hover:text-[#F97315]'" />
          </div>
          <div class="tooltip">Home</div>
        </router-link>

        <!-- Projects -->
        <router-link
          to="/projects"
          class="dock-item group relative"
          :class="$route.path === '/projects' ? 'active' : ''"
        >
          <div class="icon-container">
            <Icon name="solar:folder-bold-duotone" size="2em" :class="$route.path === '/projects' ? 'text-[#F97315]' : 'text-gray-700 group-hover:text-[#F97315]'" />
          </div>
          <div class="tooltip">Projects</div>
        </router-link>

        <!-- About -->
        <router-link
          to="/about"
          class="dock-item group relative"
          :class="$route.path === '/about' ? 'active' : ''"
        >
          <div class="icon-container">
            <Icon name="solar:user-bold-duotone" size="2em" :class="$route.path === '/about' ? 'text-[#F97315]' : 'text-gray-700 group-hover:text-[#F97315]'" />
          </div>
          <div class="tooltip">About</div>
        </router-link>

        <!-- Contact -->
        <router-link
          to="/contact"
          class="dock-item group relative"
          :class="$route.path === '/contact' ? 'active' : ''"
        >
          <div class="icon-container">
            <Icon name="solar:letter-bold-duotone" size="2em" :class="$route.path === '/contact' ? 'text-[#F97315]' : 'text-gray-700 group-hover:text-[#F97315]'" />
          </div>
          <div class="tooltip">Contact</div>
        </router-link>
      </div>
    </div>
  </div>

  <!-- Mobile Button Navigation -->
  <div class="fixed bottom-0 left-0 right-0 z-50 md:hidden">
    <div class="bg-dark border-t border-gray-800 px-4 py-2">
      <div class="flex justify-around items-center">
        <!-- Home -->
        <router-link
          to="/"
          class="mobile-nav-item flex flex-col items-center py-2 px-3 rounded-lg transition-all duration-200"
          :class="$route.path === '/' ? 'bg-[#F97315]/20' : 'hover:bg-white/10'"
        >
          <Icon name="solar:home-bold-duotone" size="2em" :class="$route.path === '/' ? 'text-[#F97315]' : 'text-white'" />
          <span class="text-xs mt-1" :class="$route.path === '/' ? 'text-[#F97315]' : 'text-white'">Home</span>
        </router-link>

        <!-- Projects -->
        <router-link
          to="/projects"
          class="mobile-nav-item flex flex-col items-center py-2 px-3 rounded-lg transition-all duration-200"
          :class="$route.path === '/projects' ? 'bg-[#F97315]/20' : 'hover:bg-white/10'"
        >
          <Icon name="solar:folder-bold-duotone" size="2em" :class="$route.path === '/projects' ? 'text-[#F97315]' : 'text-white'" />
          <span class="text-xs mt-1" :class="$route.path === '/projects' ? 'text-[#F97315]' : 'text-white'">Projects</span>
        </router-link>

        <!-- About -->
        <router-link
          to="/about"
          class="mobile-nav-item flex flex-col items-center py-2 px-3 rounded-lg transition-all duration-200"
          :class="$route.path === '/about' ? 'bg-[#F97315]/20' : 'hover:bg-white/10'"
        >
          <Icon name="solar:user-bold-duotone" size="2em" :class="$route.path === '/about' ? 'text-[#F97315]' : 'text-white'" />
          <span class="text-xs mt-1" :class="$route.path === '/about' ? 'text-[#F97315]' : 'text-white'">About</span>
        </router-link>

        <!-- Contact -->
        <router-link
          to="/contact"
          class="mobile-nav-item flex flex-col items-center py-2 px-3 rounded-lg transition-all duration-200"
          :class="$route.path === '/contact' ? 'bg-[#F97315]/20' : 'hover:bg-white/10'"
        >
          <Icon name="solar:letter-bold-duotone" size="2em" :class="$route.path === '/contact' ? 'text-[#F97315]' : 'text-white'" />
          <span class="text-xs mt-1" :class="$route.path === '/contact' ? 'text-[#F97315]' : 'text-white'">Contact</span>
        </router-link>
      </div>
    </div>
  </div>

  <!-- Top Logo Bar for Mobile -->
  <div class="md:hidden bg-dark text-light p-4 border-b border-gray-800">
    <div class="flex items-center">
      <img src="/logo.png" alt="Kaktuse Logo" class="h-8" />
      <h1 class="text-xl font-black ml-2">Kaktuse.</h1>
    </div>
  </div>

  <!-- Top Logo Bar for Desktop -->
  <div class="hidden md:block bg-transparent p-4">
    <div class="flex items-center">
      <img src="/logo.png" alt="Kaktuse Logo" class="h-10" />
      <h1 class="text-2xl font-black ml-2 text-dark">Kaktuse.</h1>
    </div>
  </div>
</template>

<script setup>
// No JavaScript needed for this navigation
</script>

<style scoped>
/* Desktop Dock Styles */
.dock-item {
  @apply relative p-1 rounded-xl transition-all duration-300 ease-out;
}

.dock-item:hover {
  @apply transform scale-125;
}

.dock-item.active .icon-container {
  @apply bg-[#F97315]/20 backdrop-blur-sm;
}

.icon-container {
  @apply p-2 rounded-lg transition-all duration-200 flex items-center justify-center;
}

.dock-item:hover .icon-container {
  @apply bg-white/20 backdrop-blur-sm;
}

/* Tooltip */
.tooltip {
  @apply absolute bottom-full left-1/2 transform -translate-x-1/2 mb-2 px-2 py-1 bg-black/80 text-white text-xs rounded opacity-0 pointer-events-none transition-opacity duration-200;
}

.dock-item:hover .tooltip {
  @apply opacity-100;
}

/* Mobile Navigation Styles */
.mobile-nav-item {
  @apply min-w-[60px];
}
</style>
