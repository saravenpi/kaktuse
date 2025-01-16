<template>
  <div class="w-full h-full bg-[#161616] text-white">
    <Navbar />

    <main class="p-5 md:p-10">
      <h1 class="text-4xl font-bold mb-8">About</h1>
      <p class="text-lg md:text-xl mb-8">
        We are a leading web development service company dedicated to delivering innovative and tailored solutions to
        meet the unique needs of our clients.
      </p>
      <p class="text-lg md:text-xl mb-8">
        Our team of experienced developers and designers work collaboratively to create high-quality, scalable, and
        user-friendly web applications.
      </p>
      <p class="text-lg md:text-xl mb-8">
        We pride ourselves on our commitment to excellence, attention to detail, and customer satisfaction. Whether
        you're a startup or an established business, we are here to help you achieve your digital goals.
      </p>
      <h1 class="text-4xl font-bold mb-8">Team</h1>
      <div class="flex flex-col md:flex-row flex-wrap">

        <div class="flex flex-col md:items-center ">
          <img src="https://avatars.githubusercontent.com/u/61117321?v=4" alt="Team Member 1"
            class="w-48 h-auto rounded-lg" />

          <h2 class="text-2xl font-semibold mt-4">Yann Thevenin</h2>

          <p class="text-lg">Lead Developer</p>

          <div class="flex space-x-4 mt-4">
            <a href="https://github.com/saravenpi" target="_blank" aria-label="GitHub Profile">
              <Icon name="mdi:github" size="2em" />
            </a>
            <a href="https://linkedin.com/in/thevyann" target="_blank" aria-label="LinkedIn Profile">
              <Icon name="mdi:linkedin" size="2em" />
            </a>
          </div>

        </div>
      </div>
    </main>
  </div>
</template>
