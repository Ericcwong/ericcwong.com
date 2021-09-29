<template>
  <div class="container">
    <Navbar class="nav-bar" />
    <Nuxt />
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
  min-height: 100vh;
  min-width: 100vw;
  position: relative;
  width: 100%;
  background-image: linear-gradient(147deg, #000000 0%, #2c3e50 74%);
}
.nav-bar {
  /* position: absolute;
  z-index: -10; */
}
</style>
