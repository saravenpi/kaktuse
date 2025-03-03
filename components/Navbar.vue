<template>
  <div class="p-3">
    <div
      class="flex flex-col gap-3 md:gap-0 md:flex-row md:items-center justify-between w-full p-6 md:py-3 md:pl-3 md:pr-6 bg-dark text-light rounded-xl">
      <router-link to="/" class="flex flex-row items-center">
        <img src="/logo-new.png" alt="Kaktuse Logo" class="h-[3rem] md:h-[3rem]" />
        <h1 class="text-[2rem] font-black ml-2">Kaktuse.</h1>
      </router-link>

      <div class="flex flex-row items-center space-x-6">
        <router-link to="/projects" class="text-xl font-medium hover:border-b-2 hover:border-white"
          active-class="border-b-2 border-[#F97315]">Projects</router-link>
        <router-link to="/about" class="text-xl font-medium hover:border-b-2 hover:border-white"
          active-class="border-b-2 border-[#F97315]">About</router-link>
        <router-link to="/contact" class="text-xl font-medium hover:border-b-2 hover:border-white"
          active-class="border-b-2 border-[#F97315]">Contact</router-link>
      </div>
    </div>
  </div>
</template>
