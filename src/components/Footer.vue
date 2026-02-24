<template>
  <footer class="bg-[#cb6ce6] text-white mt-16 pt-12 pb-10">
    <div class="max-w-7xl mx-auto grid grid-cols-1 md:grid-cols-5 gap-25 px-6">
      <router-link to="/" class="text-white hover:text-blue-300">
        <h2 class="text-xl font-semibold mb-4">Home</h2>
      </router-link>

      <router-link to="/about" class="text-white hover:text-blue-300">
        <h3 class="font-semibold mb-4">About</h3>
      </router-link>

      <router-link
        :to="{ path: '/', hash: '#portfolio' }"
        class="text-white hover:text-blue-300"
      >
        <h3 class="font-semibold mb-4">Portfolio</h3>
      </router-link>

      <router-link
        :to="{ path: '/', hash: '#testimonials' }"
        class="text-white hover:text-blue-300"
      >
        <h3 class="font-semibold mb-4">Testimonials</h3>
      </router-link>
      <div>
        <router-link
          :to="{ path: '/', hash: '#contact' }"
          class="text-white hover:text-blue-300"
        >
          <h3 class="font-semibold mb-4">Contact</h3>
        </router-link>
        <div class="flex space-x-5 mt-5">
          <a href="https://www.facebook.com/your-page" target="_blank">
            <img src="../assets/icons/icon-Facebook.png" class="w-25" />
          </a>
          <a href="https://www.x.com/mein_yjd" target="_blank">
            <img src="../assets/icons/icon-Twitter.png" class="w-25" />
          </a>
          <a href="https://www.instagram.com/astonishmotivations" target="_blank">
            <img src="../assets/icons/icon-instagram.png" class="w-25" />
          </a>
          <a href="https://www.linkedin.com/in/yahaya-joseph-017442205" target="_blank">
            <img src="../assets/icons/icon-Linkedin.png" class="w-25" />
          </a>
        </div>
      </div>
    </div>

    <p class="text-center text-xs mt-15 text-gray-200">
      © YahayaJoseph. All rights reserved
    </p>
  </footer>
</template>
