<template>
  <div class="p-3">
    <div
      class="flex gap-3 md:gap-0 flex-row md:items-center justify-between w-full p-6 md:py-3 md:pl-3 md:pr-6 bg-dark text-light rounded-xl relative">
      <router-link to="/" class="flex flex-row items-center">
        <img src="/logo.png" alt="Kaktuse Logo" class="h-[3rem] md:h-[3rem]" />
        <h1 class="text-[2rem] font-black ml-2">Kaktuse.</h1>
      </router-link>

      <!-- Desktop Menu -->
      <div class="hidden md:flex flex-row items-center space-x-6">
        <router-link to="/projects" class="text-xl font-medium hover:border-b-2 hover:border-white"
          active-class="border-b-2 border-[#F97315]">Projects</router-link>
        <router-link to="/about" class="text-xl font-medium hover:border-b-2 hover:border-white"
          active-class="border-b-2 border-[#F97315]">About</router-link>
        <router-link to="/contact" class="text-xl font-medium hover:border-b-2 hover:border-white"
          active-class="border-b-2 border-[#F97315]">Contact</router-link>
      </div>

      <!-- Burger Icon for Mobile -->
      <button
        class="md:hidden flex flex-col justify-center items-center w-10 h-10 focus:outline-none"
        @click="toggleMenu"
        aria-label="Open menu"
      >
        <span :class="['block h-1 w-8 bg-light rounded transition-all duration-300', menuOpen ? 'rotate-45 translate-y-2' : '']"></span>
        <span :class="['block h-1 w-8 bg-light rounded my-1 transition-all duration-300', menuOpen ? 'opacity-0' : '']"></span>
        <span :class="['block h-1 w-8 bg-light rounded transition-all duration-300', menuOpen ? '-rotate-45 -translate-y-2' : '']"></span>
      </button>

      <!-- Mobile Sliding Pane -->
      <transition name="slide">
        <div
          v-if="menuOpen"
          class="fixed top-0 right-0 h-full w-64 bg-dark text-light shadow-lg z-50 flex flex-col pt-24 px-8 space-y-8 transition-transform duration-300"
        >
          <button
            class="absolute top-6 right-6 text-3xl focus:outline-none"
            @click="toggleMenu"
            aria-label="Close menu"
          >
            &times;
          </button>
          <router-link
            to="/projects"
            class="text-xl font-medium hover:border-b-2 hover:border-white"
            active-class="border-b-2 border-[#F97315]"
            @click="closeMenu"
          >Projects</router-link>
          <router-link
            to="/about"
            class="text-xl font-medium hover:border-b-2 hover:border-white"
            active-class="border-b-2 border-[#F97315]"
            @click="closeMenu"
          >About</router-link>
          <router-link
            to="/contact"
            class="text-xl font-medium hover:border-b-2 hover:border-white"
            active-class="border-b-2 border-[#F97315]"
            @click="closeMenu"
          >Contact</router-link>
        </div>
      </transition>

      <!-- Overlay when menu is open -->
      <div
        v-if="menuOpen"
        class="fixed inset-0 bg-black bg-opacity-40 z-40"
        @click="closeMenu"
      ></div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      menuOpen: false,
    };
  },
  methods: {
    toggleMenu() {
      this.menuOpen = !this.menuOpen;
    },
    closeMenu() {
      this.menuOpen = false;
    },
  },
};
</script>

<style scoped>
/* Slide transition for the mobile menu */
.slide-enter-active,
.slide-leave-active {
  transition: transform 0.3s ease;
}
.slide-enter-from,
.slide-leave-to {
  transform: translateX(100%);
}
.slide-enter-to,
.slide-leave-from {
  transform: translateX(0%);
}
</style>
