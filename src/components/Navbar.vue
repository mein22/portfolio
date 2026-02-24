<template>
  <nav
    class="fixed top-0 left-0 w-full flex items-center justify-between px-12 py-6 bg-transparent text-white z-50"
  >
    <h1 class="text-3xl font-semibold text-purple-400"></h1>

    <ul class="flex items-center gap-10 text-lg">
      <router-link to="/" custom v-slot="{ navigate, isActive }">
        <li
          @click="navigate"
          :class="[
            'flex items-center gap-2 cursor-pointer',
            isActive ? 'text-purple-400 font-medium' : 'hover:text-purple-300',
          ]"
        >
          <i class="fa-solid fa-house"></i> Home
        </li>
      </router-link>

      <router-link to="/about" custom v-slot="{ navigate, isActive }">
        <li
          @click="navigate"
          :class="[
            'flex items-center gap-2 cursor-pointer',
            isActive ? 'text-purple-400 font-medium' : 'hover:text-purple-300',
          ]"
        >
          <i class="fa-regular fa-user"></i> About
        </li>
      </router-link>

      <router-link to="/projects" custom v-slot="{ navigate, isActive }">
        <li
          @click="navigate"
          :class="[
            'flex items-center gap-2 cursor-pointer',
            isActive ? 'text-purple-400 font-medium' : 'hover:text-purple-300',
          ]"
        >
          <i class="fa-solid fa-cubes"></i> Projects
        </li>
      </router-link>

      <router-link to="/resume" custom v-slot="{ navigate, isActive }">
        <li
          @click="navigate"
          :class="[
            'flex items-center gap-2 cursor-pointer',
            isActive ? 'text-purple-400 font-medium' : 'hover:text-purple-300',
          ]"
        >
          <i class="fa-regular fa-file-lines"></i> Resume
        </li>
      </router-link>

      <li class="flex items-center gap-2 relative">
        <div
          @click="handleLike"
          :title="liked ? 'Remove like' : 'Like this page'"
          class="flex items-center gap-2 bg-purple-500/20 border border-purple-400/30 px-4 py-1 rounded-xl cursor-pointer select-none active:scale-90 transition-transform"
        >
          <i
            :class="
              liked
                ? 'fa-solid fa-heart text-purple-400'
                : 'fa-regular fa-heart text-purple-300'
            "
          ></i>
          <span>{{ likes }}</span>
        </div>
      </li>
    </ul>
  </nav>
</template>

<script>
export default {
  data() {
    return {
      likes: 1,
      liked: false,
    };
  },

  mounted() {
    // Load saved state
    const savedLikes = localStorage.getItem("likes");
    const savedLiked = localStorage.getItem("liked");

    if (savedLikes !== null) this.likes = Number(savedLikes);
    if (savedLiked !== null) this.liked = savedLiked === "true";
  },

  methods: {
    handleLike() {
      if (this.liked) {
        this.likes--;
        this.liked = false;
      } else {
        this.likes++;
        this.liked = true;
      }

      // Save to localStorage
      localStorage.setItem("likes", this.likes);
      localStorage.setItem("liked", this.liked);
    },
  },
};
</script>
