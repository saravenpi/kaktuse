<template>
  <div class="h-screen flex flex-col justify-center items-start p-5 md:p-10 relative">
    <div class="flex flex-row items-center">
      <img src="/logo.png" alt="Kaktuse Logo" class="h-[5rem] md:h-[15rem]" />

      <div class="flex flex-col md:ml-4">
        <h1 class="text-[2rem] md:text-[9rem] font-black">Kaktuse.</h1>
        <h2 class="text-[1rem] md:text-[3rem] font-light">Innovative Web Development Solutions</h2>
      </div>
    </div>

    <div class="flex flex-col absolute bottom-0 right-0 p-6 md:p-10">
      <a href="mailto:contact@kaktuse.net" class="hover:underline flex items-center text-5xl md:text-4xl gap-2">
        <Icon name="uil:envelope" />
        <h1 class="hidden md:flex">contact@kaktuse.net</h1>
      </a>
    </div>
  </div>
</template>
