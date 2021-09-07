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
            "https://img.icons8.com/color/48/000000/html-5--v1.png",
            "https://img.icons8.com/color/48/000000/css3.png",
            "https://img.icons8.com/color/48/000000/javascript--v1.png",
          ],
        },
        {
          name: "Back End:",
          icons: [
            "https://img.icons8.com/color/48/000000/firebase.png",
            "https://img.icons8.com/color/50/000000/mongodb.png",
          ],
        },
        {
          name: "Software:",
          icons: [
            "https://img.icons8.com/material-outlined/48/000000/github.png",
            "https://img.icons8.com/wired/48/000000/postman-api.png",
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
  flex-wrap: wrap;
  justify-content: space-between;
  align-items: center;
  border-top: 1px solid lightslategrey;
  border-bottom: 1px solid lightslategrey;
  background: white;
  height: 100vh;
}
.skills-title {
  font-size: 2em;
}
.skill {
  display: flex;
  align-items: center;
}
</style>
