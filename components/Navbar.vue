<template>
  <div class="flex flex-col gap-3 md:gap-0 md:flex-row md:items-center justify-between w-full p-6 md:py-6 md:px-10">
    <router-link to="/" class="flex flex-row items-center">
      <img src="/logo-new.png" alt="Kaktuse Logo" class="h-[3rem] md:h-[3rem]" />
      <h1 class="text-[2rem] font-black ml-2">Kaktuse.</h1>
    </router-link>

    <div class="flex flex-row items-center space-x-6">
      <router-link to="/projects" class="text-xl font-medium hover:border-b-2 hover:border-white"
        active-class="border-b-2 border-white">Projects</router-link>
      <router-link to="/about" class="text-xl font-medium hover:border-b-2 hover:border-white"
        active-class="border-b-2 border-white">About</router-link>
      <router-link to="/contact" class="text-xl font-medium hover:border-b-2 hover:border-white"
        active-class="border-b-2 border-white">Contact</router-link>
    </div>
  </div>
</template>
