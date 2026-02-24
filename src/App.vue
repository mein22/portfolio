<template>
  <div class="min-h-screen w-full bg-[#0d0d17] overflow-hidden relative">

    <!-- background floating blobs -->
    <div
      class="absolute top-0 left-0 w-[500px] h-[500px] bg-purple-700/30 rounded-full blur-3xl pointer-events-none"
    ></div>

    <div
      class="absolute bottom-0 right-0 w-[600px] h-[600px] bg-purple-500/20 rounded-full blur-3xl pointer-events-none"
    ></div>

    <Navbar />
    <RouterView />
  </div>
</template>

<script>
import Navbar from './components/Navbar.vue'

export default {
  components: { Navbar }
}
</script>
