<template>
  <section class="container">
    <div class="introduction">
      <div class="introduction-text">
        <span
          >Hello, there! My name is Eric and I build websites while jumping from
          hobby to hobby. Currently my hobby is to plant vegetables or fruits.
        </span>
      </div>
      <img
        class="introduction-image"
        src="../SVG/guy-coding.svg"
        alt="Guy coding drawing"
      />
    </div>
    <HomeSkills />
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
  /* margin: 10% 0 10% 0; */
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
