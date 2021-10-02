<template>
  <div class="container">
    <Navbar class="nav-bar" />
    <Nuxt class="content-body" />
  </div>
</template>

<script>
import Navbar from "~/components/UI/Navigation/Navbar.vue";
import Footer from "~/components/UI/Navigation/Footer.vue";
import Sidebar from "~/components/UI/Navigation/Sidebar.vue";
export default {
  components: {
    Navbar,
    Footer,
    Sidebar,
  },
};
</script>

<style scoped>
.container {
  /* min-height: 100vh; */
  /* min-width: 100vw; */
  position: relative;
  min-width: 100%;

  background-image: linear-gradient(147deg, #000000 0%, #2c3e50 74%);
}
.content-body {
  width: 75vw;
}
</style>
