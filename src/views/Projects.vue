<template>
  <section class="w-full py-24">
    <PortfolioSection />

    <!-- GitHub CTA -->
    <div class="text-center mt-20">
      <p class="text-gray-300 mb-4">
        Check more of my work on GitHub
      </p>

      <a
        href="https://github.com/mein22"
        target="_blank"
        rel="noopener noreferrer"
        class="inline-block bg-purple-400 hover:bg-purple-900
               text-white px-8 py-3 rounded-lg transition"
      >
        GitHub
      </a>
    </div>
  </section>
  <Footer />
</template>

<script>
import PortfolioSection from "../components/PortfolioSection.vue";
import Footer from "../components/Footer.vue";

export default {
  name: "Projects",
  components: { PortfolioSection, Footer },
};
</script>
