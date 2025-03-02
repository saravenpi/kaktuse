<template>
  <div class="w-full h-screen flex flex-col justify-between bg-light text-dark bg-grid">
    <Navbar />

    <div class="flex flex-col md:ml-4 p-5 md:p-10">
      <h1 class="post-anim text-[3.5rem] md:text-[9rem] font-black font-gambarino">Kaktuse.</h1>
      <h2 class="post-anim text-[1rem] md:text-[3rem] font-light">Innovative Web Development Solutions</h2>
    </div>

    <div class="w-full flex flex-row justify-end items-end p-4 md:p-10 relative bottom-12 md:bottom-0 right-4">
      <a href="mailto:contact@kaktuse.net" class="hover:underline flex items-center text-5xl md:text-4xl gap-2">
        <div class="relative">
          <Icon name="uil:envelope" />
          <span class="absolute top-0 left-0 w-4 h-4 bg-red-500 rounded-full animate-bounce"></span>
        </div>
        <h1 class="hidden md:flex">contact@kaktuse.net</h1>
      </a>
    </div>
  </div>
</template>

<style></style>
