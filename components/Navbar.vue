<template>
  <div class="navbar-container fixed bottom-6 left-1/2 transform -translate-x-1/2 z-50 hidden md:block" :class="{ 'over-dark': isOverDarkSection }">
    <div class="navbar-background bg-white/10 backdrop-blur-lg rounded-3xl p-2 shadow-2xl border border-white/20">
      <div class="flex items-center space-x-2">
        <router-link
          to="/"
          class="dock-item group relative"
          :class="$route.path === '/' ? 'active' : ''"
        >
          <div class="icon-container">
            <Icon name="solar:home-bold-duotone" size="2em" :class="getIconClass('/', isOverDarkSection)" />
          </div>
          <div class="tooltip">Home</div>
        </router-link>

        <router-link
          to="/portfolio"
          class="dock-item group relative"
          :class="$route.path === '/portfolio' ? 'active' : ''"
        >
          <div class="icon-container">
            <Icon name="solar:folder-bold-duotone" size="2em" :class="getIconClass('/portfolio', isOverDarkSection)" />
          </div>
          <div class="tooltip">Portfolio</div>
        </router-link>

        <router-link
          to="/about"
          class="dock-item group relative"
          :class="$route.path === '/about' ? 'active' : ''"
        >
          <div class="icon-container">
            <Icon name="solar:user-bold-duotone" size="2em" :class="getIconClass('/about', isOverDarkSection)" />
          </div>
          <div class="tooltip">About</div>
        </router-link>

        <router-link
          to="/contact"
          class="dock-item group relative"
          :class="$route.path === '/contact' ? 'active' : ''"
        >
          <div class="icon-container">
            <Icon name="solar:letter-bold-duotone" size="2em" :class="getIconClass('/contact', isOverDarkSection)" />
          </div>
          <div class="tooltip">Contact</div>
        </router-link>
      </div>
    </div>
  </div>

  <div class="navbar-container-mobile fixed bottom-6 left-6 right-6 z-50 md:hidden" :class="{ 'over-dark': isOverDarkSection }">
    <div class="navbar-background bg-white/10 backdrop-blur-lg rounded-3xl p-3 shadow-2xl border border-white/20">
      <div class="flex justify-around items-center">
        <router-link
          to="/"
          class="mobile-nav-item flex flex-col items-center py-2 px-3 rounded-lg transition-all duration-200"
          :class="$route.path === '/' ? 'bg-[#F97315]/20' : 'hover:bg-white/20'"
        >
          <Icon name="solar:home-bold-duotone" size="2em" :class="getIconClass('/', isOverDarkSection)" />
          <span class="text-xs mt-1" :class="getTextClass('/', isOverDarkSection)">Home</span>
        </router-link>

        <router-link
          to="/portfolio"
          class="mobile-nav-item flex flex-col items-center py-2 px-3 rounded-lg transition-all duration-200"
          :class="$route.path === '/portfolio' ? 'bg-[#F97315]/20' : 'hover:bg-white/20'"
        >
          <Icon name="solar:folder-bold-duotone" size="2em" :class="getIconClass('/portfolio', isOverDarkSection)" />
          <span class="text-xs mt-1" :class="getTextClass('/portfolio', isOverDarkSection)">Portfolio</span>
        </router-link>

        <router-link
          to="/about"
          class="mobile-nav-item flex flex-col items-center py-2 px-3 rounded-lg transition-all duration-200"
          :class="$route.path === '/about' ? 'bg-[#F97315]/20' : 'hover:bg-white/20'"
        >
          <Icon name="solar:user-bold-duotone" size="2em" :class="getIconClass('/about', isOverDarkSection)" />
          <span class="text-xs mt-1" :class="getTextClass('/about', isOverDarkSection)">About</span>
        </router-link>

        <router-link
          to="/contact"
          class="mobile-nav-item flex flex-col items-center py-2 px-3 rounded-lg transition-all duration-200"
          :class="$route.path === '/contact' ? 'bg-[#F97315]/20' : 'hover:bg-white/20'"
        >
          <Icon name="solar:letter-bold-duotone" size="2em" :class="getIconClass('/contact', isOverDarkSection)" />
          <span class="text-xs mt-1" :class="getTextClass('/contact', isOverDarkSection)">Contact</span>
        </router-link>
      </div>
    </div>
  </div>

  <div class="md:hidden bg-dark text-light p-4 border-b border-gray-800">
    <div class="flex items-center">
      <img src="/logo.png" alt="Kaktuse Logo" class="h-8" />
      <h1 class="text-xl font-black ml-2">Kaktuse.</h1>
    </div>
  </div>

  <div class="hidden md:block bg-transparent p-4">
    <div class="flex items-center">
      <img src="/logo.png" alt="Kaktuse Logo" class="h-10" />
      <h1 class="text-2xl font-black ml-2 text-dark">Kaktuse.</h1>
    </div>
  </div>
</template>

<script setup>
import { ref, computed, onMounted, onUnmounted } from 'vue'

const isOverDarkSection = ref(false)

const checkNavbarPosition = () => {
  const navbarMobile = document.querySelector('.navbar-container-mobile')
  const navbarDesktop = document.querySelector('.navbar-container')

  const isDesktop = window.innerWidth >= 768
  const navbar = isDesktop ? navbarDesktop : navbarMobile

  if (!navbar) return

  const navbarRect = navbar.getBoundingClientRect()
  const navbarBottom = navbarRect.bottom
  const navbarTop = navbarRect.top

  const darkSections = document.querySelectorAll('.bg-dark')
  if (darkSections.length === 0) return

  let overlapping = false
  darkSections.forEach(section => {
    const sectionRect = section.getBoundingClientRect()

    if (navbarTop < sectionRect.bottom && navbarBottom > sectionRect.top) {
      overlapping = true
    }
  })

  isOverDarkSection.value = overlapping
}

const getIconClass = (routePath, overDark) => {
  const route = useRoute()
  const isActive = route.path === routePath

  if (isActive) {
    return 'text-[#F97315]'
  }

  if (overDark) {
    return 'text-white group-hover:text-[#F97315]'
  }

  return 'text-gray-700 group-hover:text-[#F97315]'
}

const getTextClass = (routePath, overDark) => {
  const route = useRoute()
  const isActive = route.path === routePath

  if (isActive) {
    return 'text-[#F97315]'
  }

  if (overDark) {
    return 'text-white'
  }

  return 'text-gray-700'
}

onMounted(() => {
  checkNavbarPosition()
  window.addEventListener('scroll', checkNavbarPosition)
  window.addEventListener('resize', checkNavbarPosition)
})

onUnmounted(() => {
  window.removeEventListener('scroll', checkNavbarPosition)
  window.removeEventListener('resize', checkNavbarPosition)
})
</script>

<style scoped>
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

.tooltip {
  @apply absolute bottom-full left-1/2 transform -translate-x-1/2 mb-2 px-2 py-1 bg-black/80 text-white text-xs rounded opacity-0 pointer-events-none transition-opacity duration-200;
}

.dock-item:hover .tooltip {
  @apply opacity-100;
}

.mobile-nav-item {
  @apply min-w-[60px];
}

.navbar-container,
.navbar-container-mobile {
  transition: all 0.3s ease-in-out;
}

.navbar-container .navbar-background,
.navbar-container-mobile .navbar-background {
  transition: background-color 0.3s ease-in-out, border-color 0.3s ease-in-out;
}

.navbar-container.over-dark .navbar-background,
.navbar-container-mobile.over-dark .navbar-background {
  @apply bg-black/20 border-black/30;
}

.dock-item .iconify,
.mobile-nav-item .iconify,
.mobile-nav-item span {
  transition: color 0.3s ease-in-out;
}

.navbar-container.over-dark .tooltip {
  @apply bg-white/90 text-black;
}
</style>
