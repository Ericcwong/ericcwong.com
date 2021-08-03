<template>
  <div class="skills">
    <span class="skills-title">Skills</span>
    <div class="skill" v-for="skill in skills" :key="skill.name">
      <span>{{ skill.name }}</span>
      <img
        v-for="icon in skill.icons"
        :key="icon"
        :src="icon"
        alt=""
        width="48px"
      />
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      skills: [
        {
          name: "Front End:",
          icons: [
            "https://img.icons8.com/color/48/000000/vue-js.png",
            "https://nuxtjs.org/logos/nuxt-emoji.png",
          ],
        },
        {
          name: "Back End:",
          icons: ["https://img.icons8.com/color/48/000000/firebase.png"],
        },
        {
          name: "Software:",
          icons: [
            "https://img.icons8.com/material-outlined/48/000000/github.png",
          ],
        },
      ],
    };
  },
};
</script>

<style scoped>
.skills {
  display: flex;
  justify-content: space-between;
  align-items: center;
  border-top: 1px solid lightslategrey;
  border-bottom: 1px solid lightslategrey;
}
.skills-title {
  font-size: 1.25rem;
}
.skill {
  display: flex;
  align-items: center;
}
</style>
