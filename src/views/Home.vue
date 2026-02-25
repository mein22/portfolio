<template>
  <!-- Herro Section --> 
  <section
  class="w-full min-h-screen flex flex-col-reverse lg:flex-row items-center justify-center lg:justify-between px-6 sm:px-10 lg:px-20 pt-28 lg:pt-32 text-white gap-12"
>
  <!-- LEFT TEXT -->
  <div class="flex flex-col gap-4 text-center lg:text-left max-w-xl">
    <h2 class="text-2xl sm:text-3xl lg:text-4xl font-light flex items-center justify-center lg:justify-start gap-2">
      {{ typedGreeting }}
    </h2>

    <h1 class="text-3xl sm:text-4xl lg:text-5xl font-bold">
      {{ typedName }}
    </h1>

    <h3 class="text-xl sm:text-2xl lg:text-3xl text-purple-400 flex items-center justify-center lg:justify-start gap-3">
      <span>
        {{ typedRole }}
        <span v-if="showCursor">|</span>
      </span>

      <RouterLink
        v-if="showAboutLink"
        to="/about"
        class="text-sm text-white/80 underline underline-offset-4 hover:text-purple-300 transition"
      >
        View more
      </RouterLink>
    </h3>
  </div>

  <!-- RIGHT IMAGE -->
  <div class="flex justify-center">
    <img
      src="../assets/about.png"
      alt="hero"
      class="w-64 sm:w-80 lg:w-[450px] xl:w-[500px]"
    />
  </div>
</section>
  <!-- First Section -->
  <!-- <section
    class="w-full h-screen flex items-center justify-between px-20 pt-32 text-white"
  >
    left
    <div class="flex flex-col gap-5">
      <h2 class="text-4xl font-light flex items-center gap-2">
        {{ typedGreeting }}
      </h2>

      <h1 class="text-5xl font-bold">
        {{ typedName }}
      </h1>

      <h3 class="text-3xl text-purple-400 flex items-center gap-4">
        <span>
          {{ typedRole }}
          <span v-if="showCursor">|</span>
        </span>

        <RouterLink
          v-if="showAboutLink"
          to="/about"
          class="text-sm text-white/80 underline underline-offset-4 hover:text-purple-300 transition"
        >
          View more
        </RouterLink>
      </h3>
    </div>

     RIGHT ILLUSTRATION
    <div>
      <img src="../assets/about.png" alt="hero" class="w-[500px]" />
    </div>
  </section> -->

  <PortfolioSection :limit="6" />

  <div class="flex justify-center mt-12">
    <RouterLink
      to="/projects"
      class="bg-purple-400 hover:bg-purple-900 text-white px-8 py-3 rounded-lg transition"
    >
      View more projects
    </RouterLink>
  </div>
  <ResumeSection />
  <TestimonialSection />
  <ContactSection />
  <Footer />
</template>

<script>
import PortfolioSection from "../components/PortfolioSection.vue";
import Footer from "../components/Footer.vue";
import ContactSection from "../components/ContactSection.vue";
import ResumeSection from "../components/ResumeSection.vue";
import TestimonialSection from "../components/TestimonialSection.vue";

export default {
  name: "Home",
  components: {
    PortfolioSection,
    ResumeSection,
    TestimonialSection,
    ContactSection,
    Footer,
  },
  data() {
    return {
      greeting: "Hi There! 👋",
      name: "I'M YAHAYA JOSEPH",
      role: "Frontend Developer",

      typedGreeting: "",
      typedName: "",
      typedRole: "",

      showCursor: true,
      showAboutLink: false,
    };
  },
  mounted() {
    this.startTyping();
    setInterval(() => {
      this.showCursor = !this.showCursor;
    }, 500);
  },
  methods: {
    startTyping() {
      this.typeText(this.greeting, "typedGreeting", 60, () => {
        this.typeText(this.name, "typedName", 60, () => {
          this.typeText(this.role, "typedRole", 80, () => {
            this.showAboutLink = true;
          });
        });
      });
    },
    typeText(text, target, speed, callback) {
      let index = 0;
      const interval = setInterval(() => {
        this[target] += text[index];
        index++;
        if (index === text.length) {
          clearInterval(interval);
          if (callback) callback();
        }
      }, speed);
    },
  },
};
</script>
