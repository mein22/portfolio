<template>
  <section id="portfolio" class="bg-[#cb6ce6] py-24">
    <div class="max-w-7xl mx-auto px-6">

      <!-- Section header -->
      <div class="text-center mb-16">
        <p class="text-sm text-white uppercase tracking-widest">
          My Recent Work
        </p>
        <h2 class="text-4xl font-bold text-white mt-2">
          Portfolio
        </h2>
      </div>

      <!-- Cards -->
      <div class="grid gap-8 md:grid-cols-2 lg:grid-cols-3">
        <div
          v-for="project in displayedProjects"
          :key="project.id"
          class="bg-[#1a1f3c] rounded-2xl p-4
                 transition-all duration-300
                 hover:scale-[1.02]
                 hover:shadow-[0_0_30px_rgba(59,130,246,0.2)]"
        >
          <!-- Image -->
          <div class="rounded-xl overflow-hidden mb-4">
            <img
              :src="project.image"
              :alt="project.title"
              class="w-full h-48 object-cover"
            />
          </div>

          <!-- Location -->
          <p class="text-xs text-gray-400 mb-1">
            {{ project.location }}
          </p>

          <!-- Title -->
          <h3 class="text-white font-semibold mb-2">
            {{ project.title }}
          </h3>

          <!-- Description -->
          <p class="text-sm text-gray-300 mb-4">
            {{ project.description }}
          </p>

          <!-- Button -->
          <a
            :href="project.link"
            target="_blank"
            rel="noopener noreferrer"
            class="inline-block bg-purple-500 text-white text-sm
                   px-4 py-2 rounded-lg
                   hover:bg-blue-500 transition-colors"
          >
            Live Demo
          </a>
        </div>
      </div>
    </div>
  </section>
</template>



<script>
export default {
  name: "PortfolioSection",
  props: {
    limit: {
      type: Number,
      default: null,
    },
  },
  data() {
    return {
      projects: [
        {
          id: 1,
          image: "/images/ecommerce.png",
          title: "E-commerce product selling marketplace platform",
          description: "An Exclusive e-commerce platform, built with Vue.js and Tailwind CSS",
          location: "Lagos, Nigeria",
          link: "https://ecommerce-mein.netlify.app",
        },
        {
          id: 2,
          image: "/images/getchange.png",
          title: "Getchange Admin",
          description: "A Financial management Admin Website. Built with Vue.js and Tailwind CSS, vuex for state management.",
          location: "Abuja, Nigeria",
          link: "https://getchange-admin.vercel.app",
        },
        {
          id: 3,
          image: "/images/myportfolio.png",
          title: "Portfolio Website",
          description: "A simple but great portfolio website showing my projects. built with vue.js",
          location: "Abuja, Nigeria",
          link: "/",
        },
        {
          id: 4,
          image: "/images/rendevous.png",
          title: "A rendevous events platform",
          description: "Rendevous platform for displaying events. Built with Vannila JavaScript and Tailwind CSS",
          location: "Lagos, Nigeria",
          link: "https://mein22.github.io/Rendevous",
        },
        {
          id: 5,
          image: "/images/sendeth.png",
          title: "A Crypto Dapp ",
          description: "A crypto platform for sending and recieving etherum. Built with Vannila JavaScript, CSS and ethers.js",
          location: "Lagos, Nigeria",
          link: "https://send-eth-d-app-eta.vercel.app/",
        },
        {
          id: 6,
          image: "/images/randomquote.png",
          title: "A random quote machine",
          description: "A random quote app for inspiration. Built with React.js and bootstrap",
          location: "Remote",
          link: "https://astonishmotivations-quote-machine.netlify.app/",
        },
        {
          id: 7,
          image: "/images/calculator.png",
          title: "A Simple Calculator",
          description: "A Calculator app for simple calculations. Built with React.js.",
          location: "Remote",
          link: "https://astonish-simple-calculator.netlify.app/",
        },
        {
          id: 8,
          image: "/images/stayhealthy.png",
          title: "Stay Healthy Extension",
          description: "A Chrome Extension to ensure safety while working. This extension reminds you to take breaks, drink water, and maintain good posture while working on your computer.",
          location: "Remote",
          link: "https://github.com/mein22/stayhealthy-extension/blob/main/README.md",
        },
        {
          id: 9,
          image: "/images/markdown.png",
          title: "A Markdown previewer",
          description: "Converts Markdown text into formatted html. A react app built",
          location: "Remote",
          link: "https://mein-markdown-previewer.netlify.app/",
        },
      ],
    };
  },
  computed: {
    displayedProjects() {
      return this.limit
        ? this.projects.slice(0, this.limit)
        : this.projects;
    },
  },
};
</script>

