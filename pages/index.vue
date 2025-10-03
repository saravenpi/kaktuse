<template>
  <div class="w-full h-[100dvh] flex flex-col justify-between bg-light text-dark bg-grid">
    <Navbar />

    <div class="flex flex-col md:ml-4 p-5 md:p-10 pt-20 md:pt-10">
      <h1 class="post-anim text-[4rem] md:text-[9rem] font-black font-gambarino">Kaktuse.</h1>
      <h2 class="post-anim text-[2.5rem] md:text-[3rem]">
        Crafting <span class="text-primary font-bold italic">impactful</span> web solutions
      </h2>
    </div>

    <div class="w-full flex flex-row justify-end items-end p-4 md:p-10 relative bottom-24 md:bottom-12 right-4">
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

<script setup>
useHead({
  title: 'Kaktuse - Crafting impactful web solutions',
  meta: [
    { name: 'description', content: 'Kaktuse is a web development agency that crafts impactful web solutions for businesses and startups.' },
    { name: 'keywords', content: 'web development, web design, web solutions, web applications, startups, businesses' },
    { name: 'author', content: 'Yann Thevenin' },
    { property: 'og:title', content: 'Kaktuse - Crafting impactful web solutions' },
    { property: 'og:description', content: 'Kaktuse is a web development agency that crafts impactful web solutions for businesses and startups.' },
    { property: 'og:image', content: 'https://kaktuse.net/og.png' },
    { property: 'og:url', content: 'https://kaktuse.net' },
    { property: 'og:type', content: 'website' },
    { name: 'twitter:card', content: 'summary_large_image' },
    { name: 'twitter:title', content: 'Kaktuse - Crafting impactful web solutions' },
    { name: 'twitter:description', content: 'Kaktuse is a web development agency that crafts impactful web solutions for businesses and startups.' },
    { name: 'twitter:image', content: 'https://kaktuse.net/og.png' }
  ],
  link: [
    { rel: 'icon', type: 'image/x-icon', href: '/favicon.ico' }
  ]
})
</script>
