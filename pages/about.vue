<template>
  <div class="w-full min-h-screen bg-light text-dark bg-grid relative overflow-hidden">
    <Navbar />

    <main class="p-5 md:p-10 pb-40 md:pb-40 pt-36 md:pt-40">
      <section class="max-w-6xl mx-auto mb-16">
        <div class="text-center mb-12">
          <div class="inline-flex items-center gap-3 bg-[#F97315]/10 rounded-full px-6 py-2 mb-6 fade-in-up">
            <Icon name="solar:user-bold-duotone" class="text-[#F97315]" size="1.2em" />
            <span class="text-[#F97315] font-medium">{{ t('nav.about') }}</span>
          </div>

          <h1 class="text-5xl md:text-7xl font-bold mb-6 font-gambarino text-dark fade-in-up" style="animation-delay: 0.2s;">{{ t('about.title') }}</h1>
          <p class="text-xl md:text-2xl text-description max-w-4xl mx-auto leading-relaxed fade-in-up" style="animation-delay: 0.4s;">
            {{ t('about.subtitle') }}
          </p>
        </div>
      </section>

      <section class="max-w-6xl mx-auto mb-20">
        <div class="grid md:grid-cols-2 gap-12 items-center">
          <div>
            <h2 class="text-3xl md:text-4xl font-bold mb-6 font-gambarino text-dark">{{ t('about.mission.title') }}</h2>
            <p class="text-lg md:text-xl mb-6 text-description leading-relaxed">
              {{ t('about.mission.text1') }}
            </p>
            <p class="text-lg md:text-xl mb-6 text-description leading-relaxed">
              {{ t('about.mission.text2') }}
            </p>
            <p class="text-lg md:text-xl text-description leading-relaxed">
              {{ t('about.mission.text3') }}
            </p>
          </div>
          <div class="flex justify-center">
            <div class="bg-dark rounded-2xl p-8 text-light max-w-md">
              <h3 class="text-2xl font-bold mb-4 font-gambarino">{{ t('about.what_sets_apart.title') }}</h3>
              <ul class="space-y-3">
                <li class="flex items-center">
                  <Icon name="mdi:check-circle" class="text-primary mr-3" size="1.5em" />
                  <span>{{ t('about.what_sets_apart.personalized') }}</span>
                </li>
                <li class="flex items-center">
                  <Icon name="mdi:check-circle" class="text-primary mr-3" size="1.5em" />
                  <span>{{ t('about.what_sets_apart.ecological') }}</span>
                </li>
                <li class="flex items-center">
                  <Icon name="mdi:check-circle" class="text-primary mr-3" size="1.5em" />
                  <span>{{ t('about.what_sets_apart.clean_code') }}</span>
                </li>
                <li class="flex items-center">
                  <Icon name="mdi:check-circle" class="text-primary mr-3" size="1.5em" />
                  <span>{{ t('about.what_sets_apart.communication') }}</span>
                </li>
              </ul>
            </div>
          </div>
        </div>
      </section>

      <section class="max-w-6xl mx-auto mb-20">
        <div class="text-center mb-12">
          <h2 class="text-4xl md:text-5xl font-bold mb-6 font-gambarino text-dark">{{ t('about.services.title') }}</h2>
          <p class="text-xl text-description">{{ t('about.services.subtitle') }}</p>
        </div>

        <div class="grid md:grid-cols-3 gap-8">
          <div class="bg-white rounded-2xl p-8 shadow-lg border border-gray-100 hover:shadow-xl transition-shadow duration-300">
            <div class="bg-[#F97315]/10 rounded-full w-16 h-16 flex items-center justify-center mb-6">
              <Icon name="mdi:brain" class="text-[#F97315]" size="2em" />
            </div>
            <h3 class="text-2xl font-bold mb-4 font-gambarino text-dark">{{ t('about.services.ai.title') }}</h3>
            <p class="text-description leading-relaxed mb-4">
              {{ t('about.services.ai.description') }}
            </p>
            <ul class="text-description space-y-2">
              <li class="flex items-center">
                <Icon name="mdi:check" class="text-[#F97315] mr-2" size="1.2em" />
                <span>{{ t('about.services.ai.features.ml') }}</span>
              </li>
              <li class="flex items-center">
                <Icon name="mdi:check" class="text-[#F97315] mr-2" size="1.2em" />
                <span>{{ t('about.services.ai.features.nlp') }}</span>
              </li>
              <li class="flex items-center">
                <Icon name="mdi:check" class="text-[#F97315] mr-2" size="1.2em" />
                <span>{{ t('about.services.ai.features.analytics') }}</span>
              </li>
            </ul>
          </div>

          <div class="bg-white rounded-2xl p-8 shadow-lg border border-gray-100 hover:shadow-xl transition-shadow duration-300">
            <div class="bg-[#F97315]/10 rounded-full w-16 h-16 flex items-center justify-center mb-6">
              <Icon name="mdi:web" class="text-[#F97315]" size="2em" />
            </div>
            <h3 class="text-2xl font-bold mb-4 font-gambarino text-dark">{{ t('about.services.web.title') }}</h3>
            <p class="text-description leading-relaxed mb-4">
              {{ t('about.services.web.description') }}
            </p>
            <ul class="text-description space-y-2">
              <li class="flex items-center">
                <Icon name="mdi:check" class="text-[#F97315] mr-2" size="1.2em" />
                <span>{{ t('about.services.web.features.responsive') }}</span>
              </li>
              <li class="flex items-center">
                <Icon name="mdi:check" class="text-[#F97315] mr-2" size="1.2em" />
                <span>{{ t('about.services.web.features.seo') }}</span>
              </li>
              <li class="flex items-center">
                <Icon name="mdi:check" class="text-[#F97315] mr-2" size="1.2em" />
                <span>{{ t('about.services.web.features.performance') }}</span>
              </li>
            </ul>
          </div>

          <div class="bg-white rounded-2xl p-8 shadow-lg border border-gray-100 hover:shadow-xl transition-shadow duration-300">
            <div class="bg-[#F97315]/10 rounded-full w-16 h-16 flex items-center justify-center mb-6">
              <Icon name="mdi:cellphone" class="text-[#F97315]" size="2em" />
            </div>
            <h3 class="text-2xl font-bold mb-4 font-gambarino text-dark">{{ t('about.services.mobile.title') }}</h3>
            <p class="text-description leading-relaxed mb-4">
              {{ t('about.services.mobile.description') }}
            </p>
            <ul class="text-description space-y-2">
              <li class="flex items-center">
                <Icon name="mdi:check" class="text-[#F97315] mr-2" size="1.2em" />
                <span>{{ t('about.services.mobile.features.cross_platform') }}</span>
              </li>
              <li class="flex items-center">
                <Icon name="mdi:check" class="text-[#F97315] mr-2" size="1.2em" />
                <span>{{ t('about.services.mobile.features.native') }}</span>
              </li>
              <li class="flex items-center">
                <Icon name="mdi:check" class="text-[#F97315] mr-2" size="1.2em" />
                <span>{{ t('about.services.mobile.features.deployment') }}</span>
              </li>
            </ul>
          </div>
        </div>
      </section>

      <section class="max-w-6xl mx-auto">
        <div class="text-center mb-12">
          <h2 class="text-4xl md:text-5xl font-bold mb-6 font-gambarino text-dark">{{ t('about.about_me.title') }}</h2>
          <p class="text-xl text-description">{{ t('about.about_me.subtitle') }}</p>
        </div>

        <div class="flex justify-center">
          <div class="rounded-3xl p-8 shadow-lg max-w-md text-center profile-card" style="background: #FFF; border: 2px solid #7D6666;">
            <div class="relative mb-6">
              <img src="https://avatars.githubusercontent.com/u/61117321?v=4" alt="Yann Thevenin"
                class="w-32 h-32 rounded-full mx-auto object-cover border-4 border-primary" />
            </div>

            <h3 class="text-2xl font-bold text-dark font-gambarino mb-2">{{ t('about.about_me.name') }}</h3>
            <p class="text-lg text-primary font-medium mb-4">{{ t('about.about_me.role') }}</p>
            <p class="text-description mb-6 leading-relaxed">
              {{ t('about.about_me.description') }}
            </p>

            <div class="flex justify-center space-x-4">
              <a href="https://github.com/saravenpi" target="_blank"
                class="social-card text-[#F97315] p-3 rounded-full transition-all duration-300 flex items-center justify-center bg-[#F97315]/10"
                aria-label="GitHub Profile">
                <Icon name="mdi:github" size="1.5em" />
              </a>

              <a href="https://linkedin.com/in/thevyann" target="_blank"
                class="social-card text-[#F97315] p-3 rounded-full transition-all duration-300 flex items-center justify-center bg-[#F97315]/10"
                aria-label="LinkedIn Profile">
                <Icon name="mdi:linkedin" size="1.5em" />
              </a>
            </div>
          </div>
        </div>
      </section>

      <section class="max-w-6xl mx-auto mt-20">
        <div class="text-center mb-12">
          <h2 class="text-4xl md:text-5xl font-bold mb-6 font-gambarino text-dark">{{ t('about.technologies.title') }}</h2>
          <p class="text-xl text-description">{{ t('about.technologies.subtitle') }}</p>
        </div>

        <div class="grid grid-cols-2 md:grid-cols-6 gap-6">
          <div class="bg-white rounded-xl p-6 text-center shadow-sm border border-gray-100 hover:shadow-lg transition-shadow duration-200">
            <Icon name="mdi:vuejs" class="text-green-500 mx-auto mb-3" size="3em" />
            <h4 class="font-semibold text-dark">Vue.js</h4>
          </div>
          <div class="bg-white rounded-xl p-6 text-center shadow-sm border border-gray-100 hover:shadow-lg transition-shadow duration-200">
            <Icon name="mdi:react" class="text-cyan-500 mx-auto mb-3" size="3em" />
            <h4 class="font-semibold text-dark">React</h4>
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
          <div class="bg-white rounded-xl p-6 text-center shadow-sm border border-gray-100 hover:shadow-lg transition-shadow duration-200">
            <Icon name="mdi:tailwind" class="text-blue-500 mx-auto mb-3" size="3em" />
            <h4 class="font-semibold text-dark">Tailwind</h4>
          </div>
        </div>
      </section>
    </main>
  </div>
</template>

<script setup>
const { t } = useI18n()

useHead({
  title: t('meta.about.title'),
})
</script>

<style scoped>
.fade-in-up {
  animation: fadeInUp 0.8s ease-out forwards;
  opacity: 0;
  transform: translateY(30px);
}

@keyframes fadeInUp {
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.profile-card {
  transition: transform 0.3s, box-shadow 0.3s;
}

.profile-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 20px 40px rgba(0, 0, 0, 0.1);
}

.social-card {
  transition: all 0.3s ease;
  opacity: 1;
  position: relative;
  overflow: hidden;
}

.social-card:hover {
  transform: translateY(-5px) scale(1.05) rotate(3deg);
  box-shadow: 0 20px 40px rgba(249, 115, 21, 0.3);
  background: linear-gradient(135deg, #F97315, #ff8533);
  color: white;
}

.social-card:hover .iconify {
  transform: scale(1.2) rotate(-3deg);
  filter: drop-shadow(0 2px 4px rgba(0, 0, 0, 0.2));
}

.social-card .iconify {
  transition: all 0.3s ease;
}
</style>
