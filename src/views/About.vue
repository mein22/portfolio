<template>
  <div
    class="min-h-screen w-full h-full text-gray-200 bg-cover bg-center bg-no-repeat pb-20"
  >
      <div class="text-center mb-16 mt-16">
        <p
          class="text-sm font-semibold text-gray-200 uppercase tracking-widest"
        >
          Get to know
        </p>
        <h2 class="text-4xl font-bold text-[#cb6ce6] mt-2">About Me</h2>
      </div>
    <!-- SECTION 1: Our Story -->
    <div class="grid grid-cols-1 md:grid-cols-2 gap-10 items-center">
      <!-- Left Text -->
      <div class="pl-10">
        <p class="text-lg leading-relaxed text-gray-200 ">
          <b>
            I’m a Frontend Developer with over 3 years of experience building
            and maintaining modern web applications. I primarily work with
            JavaScript and frameworks like Vue.js and React, where I enjoy
            turning designs and product ideas into clean, responsive, and
            reliable user interfaces. In Vue, I’ve worked extensively with Vue
            3, the Composition API, and state management tools like Vuex and
            Pinia to build scalable and easy-to-maintain applications. I focus
            on writing clear, reusable code and structuring projects in a way
            that makes collaboration and future updates easier. <br></br>
            I also have
            solid experience with React, building performant applications using
            modern patterns such as hooks, context, and component-driven
            architecture. I’ve contributed to improving performance through
            techniques like code splitting, lazy loading, and optimizing
            component rendering. Beyond coding, I enjoy collaborating with
            designers and backend developers, reviewing code, and continuously
            learning better ways to build great products. I’m comfortable taking
            ownership of features, contributing to technical decisions, and
            growing alongside a team that values quality and continuous
            improvement.
          </b>
        </p>
        <button
          @click="ToContact"
          class="bg-[#cb6ce6] hover:bg-purple-500 text-white font-bold py-3 px-4 rounded"
        >
          Let's talk
        </button>
      </div>

      <!-- Right Image -->
      <img
        src="@/assets/about-image.png"
        alt="About Image"
        class="rounded-lg w-full bg-white object-cover mr-auto"
      />
    </div>

  <section
    class="w-full py-20 text-white"
  >
    <div class="max-w-6xl mx-auto px-6 grid md:grid-cols-2 gap-12 items-center">

      <!-- LEFT SIDE -->
      <div class="flex flex-col items-center text-center md:text-left">

        <!-- Image -->
        <img
          src="@/assets/portfolio.png"
          alt="Instructor"
          class="w-64 h-64 rounded-full object-cover mb-6"
        />

        <!-- Name -->
        <h3 class="text-lg font-semibold">
          Yahaya Joseph 
        </h3>
        <p class="text-gray-400 text-sm mb-6">
          Software Developer (Frontend)
        </p>

        <!-- Social Icons -->
        <div class="flex gap-4">
          <a
            href="https://www.linkedin.com/in/yahaya-joseph-017442205"
            class="w-12 h-12 rounded-full border border-[#cb6ce6] flex items-center justify-center hover:bg-lime-400/10 transition"
          >
            <i class="fa-brands fa-linkedin-in"></i>
          </a>

          <a
            href="https://www.instagram.com/astonishmotivations"
            class="w-12 h-12 rounded-full border border-[#cb6ce6] flex items-center justify-center hover:bg-lime-400/10 transition"
          >
            <i class="fa-brands fa-instagram"></i>
          </a>

          <a
            href="https://www.x.com/mein_yjd"
            class="w-12 h-12 rounded-full border border-[#cb6ce6] flex items-center justify-center hover:bg-lime-400/10 transition"
          >
            <i class="fa-brands fa-x-twitter"></i>
          </a>
        </div>
      </div>

      <!-- RIGHT SIDE -->
      <div>
        <h2 class="text-4xl md:text-5xl font-bold leading-tight mb-6">
          <span class="text-[#cb6ce6]">Meet</span> your favorite developer
        </h2>

        <p class="text-gray-300 leading-relaxed">
          A developer, creator and designer, Yahaya is a Front-End specialist
          known for innovative solutions and passion for collaboration.
          As a multiskilled developer, he contributes to the Tech ecosystem.
          You can also find him mentoring aspiring developers and sharing knowledge.
        </p>
      </div>

    </div>
  </section>


    <!-- SECTION 3: Stats -->
    <div class="mt-20">
       
      <div class="grid grid-cols-2 md:grid-cols-4 gap-6 max-w-7xl mx-auto px-6">
        <!-- Box 1 -->
        <div
          class="border rounded-lg py-8 flex flex-col items-center text-center"
        >
          <div
            class="h-16 w-16 bg-black border-4 border-gray-300 rounded-full flex items-center justify-center mb-4"
          >
          <i class="fa fa-shield" aria-hidden="true"></i>
          </div>
          <h3 class="text-2xl font-bold">Experience</h3>
          <h3 class="text-2xl font-bold">3+</h3>
          <p class="text-gray-600 mt-1">Working</p>
        </div>

         <!-- Box 2 -->
        <div
          class="border rounded-lg py-8 flex flex-col items-center text-center"
        >
          <div
            class="h-16 w-16 bg-black border-4 border-gray-300 rounded-full flex items-center justify-center mb-4"
          >
            <i class="fa fa-user" aria-hidden="true"></i>
          </div>
          <h3 class="text-2xl font-bold">Clients</h3>
          <h3 class="text-2xl font-bold">10+</h3>
          <p class="text-gray-600 mt-1">Worldwide</p>
        </div>

        <!-- Box 3 -->
        <div
          class="border rounded-lg py-8 flex flex-col items-center text-center"
        >
          <div
            class="h-16 w-16 bg-black border-4 border-gray-300 rounded-full flex items-center justify-center mb-4"
          >
            <i class="fa fa-product-hunt" aria-hidden="true"></i>
          </div>
          <h3 class="text-2xl font-bold">Projects Built</h3>
          <h3 class="text-2xl font-bold">20+</h3>
        </div>

        <!-- Box 4 -->
        <div
          class="border rounded-lg py-8 flex flex-col items-center text-center"
        >
          <div
            class="h-16 w-16 bg-black border-4 border-gray-300 rounded-full flex items-center justify-center mb-4"
          >
           <i class="fa fa-certificate" aria-hidden="true"></i>
          </div>
          <h3 class="text-2xl font-bold">Certifications</h3>
          <h3 class="text-2xl font-bold">20+</h3>
          <p class="text-gray-600 mt-1">Still Acquiring</p>
        </div>
      </div>
    </div>

    <!-- SECTION 3: Team Members -->
    <div>
      <SkillSection />
    </div>
  </div>
  <Footer />
</template>

<script>
import homeBg from "../assets/home-bg.jpg";
import Footer from "../components/Footer.vue";
import SkillSection from "../components/SkillSection.vue";

export default {
  name: "AboutPage",
  components: {
    Footer,
    SkillSection
  },
  data() {
    return {
      homeBg
    };
  },
  methods: {
    ToContact() {
      this.$router.push({ path: '/', hash: '#contact' });
    }
  }
};
</script>