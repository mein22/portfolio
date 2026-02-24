<template>
  <section id="testimonials" class="w-full py-24 text-white relative overflow-hidden">
    <div class="max-w-4xl mx-auto px-6 text-center">

      <!-- Header -->
      <p class="text-gray-400 mb-2">
        Review from Clients and people I have worked with
      </p>
      <h2 class="text-4xl font-bold text-[#cb6ce6] mb-16">
        Testimonials
      </h2>

      <!-- Slider Card -->
      <transition name="fade" mode="out-in">
        <div
          :key="currentIndex"
          class="bg-[#1a1f3c] rounded-3xl px-10 py-14 shadow-lg"
        >
          <img
            :src="testimonials[currentIndex].image"
            alt="avatar"
            class="w-20 h-20 rounded-full mx-auto mb-6 border-4 border-[#cb6ce6]"
          />

          <h3 class="font-semibold text-lg mb-4">
            {{ testimonials[currentIndex].name }}
          </h3>

          <p class="text-gray-200 leading-relaxed max-w-xl mx-auto">
            {{ testimonials[currentIndex].message }}
          </p>
        </div>
      </transition>

      <!-- Dots -->
      <div class="flex justify-center gap-3 mt-10">
        <button
          v-for="(item, index) in testimonials"
          :key="index"
          @click="goToSlide(index)"
          class="w-3 h-3 rounded-full transition"
          :class="index === currentIndex ? 'bg-blue-400 w-6' : 'bg-gray-500'"
        />
      </div>

    </div>
  </section>
</template>

<script>
export default {
  name: "TestimonialSection",
  data() {
    return {
      currentIndex: 0,
      intervalId: null,
      testimonials: [
        {
          name: "Sarah Jibrin, Leshdel Clothing",
          image: "/images/mrssarah.jpg",
          message:
            "Yahaya is currently working on the development of a Vue3 frontend for my clothing brand. He delivered features in a timely manner and is highly dedicated to ensuring quality delivery.",
        },
        {
          name: "Job Joseph, Astonish De world ltd",
          image: "/images/mrjob.jpg",
          message:
            "Working with Yahaya was easy. His attention to detail and UI skills helped us to improve user engagement significantly.",
        },
        {
          name: "Ogu Solomon, CEO, Sacs inc.",
          image: "/images/mrsolo.jpg",
          message:
            "I mentored Yahaya, he is a reliable frontend engineer who communicates clearly and consistently delivers high-quality work. Highly recommended.",
        },
      ],
    };
  },
  mounted() {
    this.startAutoSlide();
  },
  beforeUnmount() {
    clearInterval(this.intervalId);
  },
  methods: {
    startAutoSlide() {
      this.intervalId = setInterval(() => {
        this.currentIndex =
          (this.currentIndex + 1) % this.testimonials.length;
      }, 20000); // 20 seconds
    },
    goToSlide(index) {
      this.currentIndex = index;
      this.restartTimer();
    },
    restartTimer() {
      clearInterval(this.intervalId);
      this.startAutoSlide();
    },
  },
};
</script>

<style>
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.6s ease;
}
.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}
</style>