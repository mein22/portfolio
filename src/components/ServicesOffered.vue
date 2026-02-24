<template>
  <section class="py-16 bg-white">
    <div class="max-w-6xl mx-auto px-6 grid md:grid-cols-2 gap-8 items-center">
      <div class="-mt-8">
        <h2 class="text-3xl font-bold leading-snug mb-4 text-[#000000]">Discover a World of Events <br/> Tailored Just for You.</h2>
        <button class="bg-purple-600 hover:bg-purple-700 text-white font-medium px-6 py-2 rounded-lg shadow">
          <a href="#trending">View all events</a>
        </button>
      </div>

      <div class="grid grid-cols-2 gap-4">
        <div v-for="(item, i) in categories" :key="i" class="relative overflow-hidden rounded-lg">
          <img :src="item.image" :alt="item.title" class="w-full h-40 md:h-48 object-cover" />
          <div class="absolute inset-0 bg-black/30 flex items-center justify-center">
            <span class="text-white font-semibold text-lg">{{ item.title }}</span>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import online from '@/assets/frontend.png'
import physical from '@/assets/teamplayer.png'
import hybrid from '@/assets/uiimage.png'

export default {
  name: 'Discover',
  data() {
    return {
      categories: [
        { title: 'Online Events', image: online },
        { title: 'Physical Events', image: physical },
        { title: 'Hybrid Events', image: hybrid }
      ]
    }
  }
}
</script>






