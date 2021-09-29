<template>
  <div class="skills">
    <p class="skills-title">Skills</p>
    <div class="title" v-for="skill in skills" :key="skill.name">
      <p>{{ skill.area }}</p>
      <div class="card" v-for="name in skill.names" :key="name">
        <div class="card-header">{{ name }}</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      skills: [
        {
          area: "Front End:",
          names: ["Vue", "Nuxt", "HTML", "CSS", "Javascript"],
        },
        {
          area: "Back End:",
          names: ["Firebase", "MongoDB"],
        },
        // {
        //   area: "Software:",
        //   name: [
        //     "https://img.icons8.com/material-outlined/48/000000/github.png",
        //     "https://img.icons8.com/wired/48/000000/postman-api.png",
        //   ],
        // },
      ],
    };
  },
};
</script>

<style scoped>
.skills {
  display: flex;
  flex-wrap: wrap;
  border-top: 1px solid lightslategrey;
  border-bottom: 1px solid lightslategrey;
  color: white;
}
.skills-title {
  font-size: 2em;
}
</style>
