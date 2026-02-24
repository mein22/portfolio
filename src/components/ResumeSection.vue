<template>
  <section class="w-full py-24 bg-transparent">
    <div class="max-w-7xl mx-auto px-6 flex justify-center">

      <!-- Resume Card -->
      <div
        class="bg-white rounded-2xl shadow-lg px-8 py-12
               w-full max-w-xl text-center"
      >
        <h2 class="text-3xl font-bold text-gray-800 mb-6">
          Check out my resume
        </h2>

        <a
          href="/resume/Yahaya_Joseph_CV.pdf"
          download
          class="inline-block bg-purple-400 hover:bg-purple-900
                 text-white font-semibold px-8 py-3
                 rounded-lg transition"
        >
          Download CV
        </a>
      </div>

    </div>
  </section>
</template>

<script>
export default {
  name: "ResumeSection",
};
</script>
