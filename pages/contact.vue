<template>
  <div class="w-full min-h-screen bg-light bg-grid text-dark">
    <Navbar />

    <main class="p-5 md:p-10 flex flex-col items-center">
      <h1 class="text-4xl font-bold mb-4 font-gambarino text-center flex items-center gap-2">
        <Icon name="solar:letter-bold-duotone" class="text-3xl text-description" />
        Get in touch
      </h1>
      <p class="text-xl mb-8 text-center">Let's get in touch ! Fill out the form below or email directly at <a
          href="mailto:contact@kaktuse.net" class="text-[#F97315] underline">contact@kaktuse.net</a>.</p>
      <form class="w-full max-w-lg rounded-xl shadow-lg p-8 flex flex-col gap-6 project-card"
        @submit.prevent="handleSubmit">
        <div>
          <label for="name" class="block text-lg font-medium mb-1">Name</label>
          <input id="name" v-model="form.name" type="text"
            class="w-full px-4 py-2 border border-gray-300 rounded focus:outline-none focus:ring-2 focus:ring-[#F97315]"
            :class="{ 'border-red-400': errors.name }" placeholder="Your name" required />
          <p v-if="errors.name" class="text-red-500 text-sm mt-1">{{ errors.name }}</p>
        </div>
        <div>
          <label for="email" class="block text-lg font-medium mb-1">Email</label>
          <input id="email" v-model="form.email" type="email"
            class="w-full px-4 py-2 border border-gray-300 rounded focus:outline-none focus:ring-2 focus:ring-[#F97315]"
            :class="{ 'border-red-400': errors.email }" placeholder="you@email.com" required />
          <p v-if="errors.email" class="text-red-500 text-sm mt-1">{{ errors.email }}</p>
        </div>
        <div>
          <label for="message" class="block text-lg font-medium mb-1">Message</label>
          <textarea id="message" v-model="form.message" rows="5"
            class="w-full px-4 py-2 border border-gray-300 rounded focus:outline-none focus:ring-2 focus:ring-[#F97315]"
            :class="{ 'border-red-400': errors.message }" placeholder="How can we help you?" required></textarea>
          <p v-if="errors.message" class="text-red-500 text-sm mt-1">{{ errors.message }}</p>
        </div>
        <button type="submit"
          class="bg-[#F97315] hover:bg-[#ea580c] text-white font-bold py-2 px-6 rounded transition-colors duration-200 flex items-center justify-center gap-2"
          :disabled="loading">
          <span v-if="loading">Sending...</span>
          <span v-else class="flex items-center gap-2">
            <Icon name="solar:plain-bold-duotone" class="text-xl" />
            Send Message
          </span>
        </button>
        <p v-if="success" class="text-green-600 text-center font-medium mt-2">Thank you! Your message has been sent.</p>
        <p v-if="errorMsg" class="text-red-600 text-center font-medium mt-2">{{ errorMsg }}</p>
      </form>
    </main>
  </div>
</template>

<script setup>
import { ref, reactive } from 'vue'

useHead({
  title: 'Kaktuse - Contact',
})

const form = reactive({
  name: '',
  email: '',
  message: '',
})

const errors = reactive({
  name: '',
  email: '',
  message: '',
})

const loading = ref(false)
const success = ref(false)
const errorMsg = ref('')

function validateEmail(email) {
  // Simple email regex
  return /^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(email)
}

function validateForm() {
  errors.name = form.name.trim() ? '' : 'Name is required.'
  errors.email = form.email.trim()
    ? (validateEmail(form.email) ? '' : 'Please enter a valid email.')
    : 'Email is required.'
  errors.message = form.message.trim() ? '' : 'Message is required.'
  return !errors.name && !errors.email && !errors.message
}

function handleSubmit() {
  success.value = false
  errorMsg.value = ''
  if (!validateForm()) return

  // Construct mailto link with prefilled subject and body
  const subject = encodeURIComponent('Contact from ' + form.name)
  const body = encodeURIComponent(
    `Name: ${form.name}\nEmail: ${form.email}\n\n${form.message}`
  )
  const mailto = `mailto:contact@kaktuse.net?subject=${subject}&body=${body}`

  // Redirect to mailto link
  window.location.href = mailto

  // Optionally reset form
  form.name = ''
  form.email = ''
  form.message = ''
}
</script>

<style scoped>
.project-card {
  transition: transform 0.3s, opacity 0.5s;
  opacity: 0;
  animation: fadeIn 1s forwards;
  background: #FFF;
  border: 2px solid #7D6666;
}

@keyframes fadeIn {
  from {
    opacity: 0;
  }

  to {
    opacity: 1;
  }
}

.project-card:hover {
  transform: translateY(-5px);
}
</style>
