<template>
  <div class="w-full h-screen flex flex-col justify-between">
    <!-- Top nav -->
    <Navbar />

    <!-- Center -->
    <div class="flex flex-col md:ml-4 p-5 md:p-10">
      <h1 class="text-[2rem] md:text-[9rem] font-black">Kaktuse.</h1>
      <h2 class="text-[1rem] md:text-[3rem] font-light">Innovative Web Development Solutions</h2>
    </div>

    <!-- Footer -->
    <div class="w-full flex flex-row justify-end items-end p-4 md:p-10">
      <a href="mailto:contact@kaktuse.net" class="hover:underline flex items-center text-5xl md:text-4xl gap-2">
        <Icon name="uil:envelope" />
        <h1 class="hidden md:flex">contact@kaktuse.net</h1>
      </a>
    </div>

  </div>
</template>
