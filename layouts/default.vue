<template>
  <div class="page-container">
    <div class="page-side-bar">
      <Sidebar />
    </div>
    <div class="page-body">
      <Navbar />
      <Nuxt />
      <Footer />
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
  display: grid;
  height: 100%;
  grid-template-columns: 10% 80% 10%;
  grid-template-areas: "sidebar body .";
}
.page-body {
  grid-area: body;
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