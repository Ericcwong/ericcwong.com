<template>
  <section class="container">
    <div class="introduction">
      <div class="introduction-text">
        <span> Hi, how's it going? My name is Eric</span>
        <HomeSkills />
      </div>
      <img
        class="introduction-image"
        src="../SVG/guy-coding.svg"
        alt="Guy coding drawing"
      />
    </div>

    <HomeContent />
  </section>
</template>

<script>
import HomeContent from "~/components/UI/Landing-Page/HomeContent.vue";
import HomeSkills from "~/components/UI/Landing-Page/HomeSkills.vue";
export default {
  components: {
    HomeContent,
    HomeSkills,
  },
};
</script>

<style scoped>
.introduction {
  display: grid;
  grid-template-columns: 1fr 1fr;
}
.introduction-text {
  display: flex;
  flex-wrap: wrap;
  align-items: center;
  font-size: 2rem;
}

.introduction-image {
  width: 100%;
}
</style>