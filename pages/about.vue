<template>
  <div class="min-h-screen w-full bg-light bg-grid text-dark">
    <Navbar />

    <main class="p-5 md:p-10 pb-32 md:pb-32 pt-20 md:pt-10">
      <!-- Hero Section -->
      <section class="max-w-6xl mx-auto mb-16">
        <div class="text-center mb-12">
          <h1 class="text-5xl md:text-7xl font-bold mb-6 font-gambarino text-dark">About Kaktuse</h1>
          <p class="text-xl md:text-2xl text-description max-w-4xl mx-auto leading-relaxed">
            Crafting digital experiences that bloom in the digital desert
          </p>
        </div>
      </section>

      <!-- Mission Section -->
      <section class="max-w-6xl mx-auto mb-20">
        <div class="grid md:grid-cols-2 gap-12 items-center">
          <div>
            <h2 class="text-3xl md:text-4xl font-bold mb-6 font-gambarino text-dark">My Mission</h2>
            <p class="text-lg md:text-xl mb-6 text-description leading-relaxed">
              I am a dedicated web developer committed to delivering innovative and tailored solutions to meet the unique
              needs of my clients.
            </p>
            <p class="text-lg md:text-xl mb-6 text-description leading-relaxed">
              I work collaboratively with clients to create high-quality, scalable, and user-friendly web applications
              that drive real business results.
            </p>
            <p class="text-lg md:text-xl text-description leading-relaxed">
              I pride myself on my commitment to excellence, attention to detail, and ensuring customer satisfaction. Whether
              you're a startup or an established business, I'm here to help you achieve your digital goals.
            </p>
          </div>
          <div class="flex justify-center">
            <div class="bg-dark rounded-2xl p-8 text-light max-w-md">
              <h3 class="text-2xl font-bold mb-4 font-gambarino">What Sets Me Apart</h3>
              <ul class="space-y-3">
                <li class="flex items-center">
                  <Icon name="mdi:check-circle" class="text-primary mr-3" size="1.5em" />
                  <span>Personalized Approach</span>
                </li>
                <li class="flex items-center">
                  <Icon name="mdi:check-circle" class="text-primary mr-3" size="1.5em" />
                  <span>Modern Technologies</span>
                </li>
                <li class="flex items-center">
                  <Icon name="mdi:check-circle" class="text-primary mr-3" size="1.5em" />
                  <span>Clean Code Practice</span>
                </li>
                <li class="flex items-center">
                  <Icon name="mdi:check-circle" class="text-primary mr-3" size="1.5em" />
                  <span>Direct Communication</span>
                </li>
              </ul>
            </div>
          </div>
        </div>
      </section>

      <!-- About Me Section -->
      <section class="max-w-6xl mx-auto">
        <div class="text-center mb-12">
          <h2 class="text-4xl md:text-5xl font-bold mb-6 font-gambarino text-dark">About Me</h2>
          <p class="text-xl text-description">The developer behind Kaktuse</p>
        </div>

        <div class="flex justify-center">
          <div class="bg-white rounded-3xl p-8 shadow-lg max-w-md text-center border border-gray-100">
            <div class="relative mb-6">
              <img src="https://avatars.githubusercontent.com/u/61117321?v=4" alt="Yann Thevenin"
                class="w-32 h-32 rounded-full mx-auto object-cover border-4 border-primary" />
            </div>

            <h3 class="text-2xl font-bold text-dark font-gambarino mb-2">Yann Thevenin</h3>
            <p class="text-lg text-primary font-medium mb-4">Lead Developer & Founder</p>
            <p class="text-description mb-6 leading-relaxed">
              Passionate about creating exceptional digital experiences with modern technologies and clean code architecture.
            </p>

            <div class="flex justify-center space-x-4">
              <a href="https://github.com/saravenpi" target="_blank"
                class="bg-dark text-white p-3 rounded-full hover:bg-gray-800 transition-colors duration-200 flex items-center justify-center"
                aria-label="GitHub Profile">
                <Icon name="mdi:github" size="1.5em" />
              </a>

              <a href="https://linkedin.com/in/thevyann" target="_blank"
                class="bg-blue-600 text-white p-3 rounded-full hover:bg-blue-700 transition-colors duration-200 flex items-center justify-center"
                aria-label="LinkedIn Profile">
                <Icon name="mdi:linkedin" size="1.5em" />
              </a>
            </div>
          </div>
        </div>
      </section>

      <!-- Technologies Section -->
      <section class="max-w-6xl mx-auto mt-20">
        <div class="text-center mb-12">
          <h2 class="text-4xl md:text-5xl font-bold mb-6 font-gambarino text-dark">Technologies I Use</h2>
          <p class="text-xl text-description">Modern tools for modern solutions</p>
        </div>

        <div class="grid grid-cols-2 md:grid-cols-6 gap-6">
          <div class="bg-white rounded-xl p-6 text-center shadow-sm border border-gray-100 hover:shadow-lg transition-shadow duration-200">
            <Icon name="mdi:vuejs" class="text-green-500 mx-auto mb-3" size="3em" />
            <h4 class="font-semibold text-dark">Vue.js</h4>
          </div>
          <div class="bg-white rounded-xl p-6 text-center shadow-sm border border-gray-100 hover:shadow-lg transition-shadow duration-200">
            <Icon name="mdi:nuxt" class="text-green-400 mx-auto mb-3" size="3em" />
            <h4 class="font-semibold text-dark">Nuxt</h4>
          </div>
          <div class="bg-white rounded-xl p-6 text-center shadow-sm border border-gray-100 hover:shadow-lg transition-shadow duration-200">
            <Icon name="mdi:tailwind" class="text-blue-500 mx-auto mb-3" size="3em" />
            <h4 class="font-semibold text-dark">Tailwind</h4>
          </div>
          <div class="bg-white rounded-xl p-6 text-center shadow-sm border border-gray-100 hover:shadow-lg transition-shadow duration-200">
            <Icon name="mdi:language-typescript" class="text-blue-600 mx-auto mb-3" size="3em" />
            <h4 class="font-semibold text-dark">TypeScript</h4>
          </div>
          <div class="bg-white rounded-xl p-6 text-center shadow-sm border border-gray-100 hover:shadow-lg transition-shadow duration-200">
            <Icon name="simple-icons:svelte" class="text-orange-500 mx-auto mb-3" size="3em" />
            <h4 class="font-semibold text-dark">SvelteKit</h4>
          </div>
          <div class="bg-white rounded-xl p-6 text-center shadow-sm border border-gray-100 hover:shadow-lg transition-shadow duration-200">
            <Icon name="mdi:language-go" class="text-blue-400 mx-auto mb-3" size="3em" />
            <h4 class="font-semibold text-dark">Golang</h4>
          </div>
        </div>
      </section>
    </main>
  </div>
</template>

<script setup>
useHead({
  title: 'Kaktuse - About',
})
</script>
