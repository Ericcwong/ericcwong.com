<template>
  <div class="page-container">
    <div class="page-body">
      <Navbar class="nav" />
      <Nuxt />
    </div>
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
.page-container {
  width: 100%;
  background-image: linear-gradient(147deg, #000000 0%, #2c3e50 74%);
}
.page-body {
  grid-area: body;
}
.nav {
  width: 100%;
  position: absolute;
  z-index: 100;
}
.page-side-bar {
  display: flex;
  align-items: center;
  grid-area: sidebar;
}
@media only screen and (max-width: 880px) {
  .page-side-bar {
    display: none;
  }
}
</style>
