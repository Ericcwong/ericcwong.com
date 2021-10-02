<template>
  <div class="content">
    <HomePanel />
    <HomeSkills />
  </div>
</template>

<script>
import HomePanel from "~/components/UI/Landing-Page/HomePanel.vue";
import HomeSkills from "~/components/UI/Landing-Page/HomeSkills.vue";
export default {
  components: {
    HomePanel,
    HomeSkills,
  },
};
</script>

<style scoped></style>
