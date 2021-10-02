<template>
  <section class="skills">
    <p class="skill-title">Skills</p>
    <div class="skill-cards" v-for="skill in skills" :key="skill.area">
      <div class="card">
        <p class="card-title">{{ skill.area }}</p>
        <div class="card-content" v-for="card in skill.cards" :key="card.name">
          <img :src="card.icon" alt="" />
          <div class="card-name">{{ card.name }}</div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      skills: [
        {
          area: "Front End:",
          cards: [
            {
              name: "Vue",
              icon: "https://img.icons8.com/color/48/000000/vue-js.png",
            },
            {
              name: "Nuxt",
              icon: "https://nuxtjs.org/design-kit/colored-logo.svg",
            },
            {
              name: "HTML",
              icon: "https://img.icons8.com/color/48/000000/html-5--v1.png",
            },
            {
              name: "CSS",
              icon: "https://img.icons8.com/color/48/000000/css3.png",
            },
            {
              name: "JavaScript",
              icon: "https://img.icons8.com/color/48/000000/javascript--v1.png",
            },
          ],
        },
        {
          area: "Back End:",
          cards: [
            {
              name: "Firebase",
              icon: "https://img.icons8.com/color/48/000000/firebase.png",
            },
            {
              name: "MongoDB",
              icon: "https://img.icons8.com/color/48/000000/mongodb.png",
            },
          ],
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
  justify-content: space-evenly;
  color: white;
  flex-wrap: wrap;
  gap: 1rem;
  border-top: 1px solid lightslategrey;
  border-bottom: 1px solid lightslategrey;
}
.skill-title {
  font-size: 3rem;
  flex: 0 0 100%;
}
.skill-card {
  display: flex;
  color: black;
  background: white;
  height: 10rem;
}
.card {
  font-size: 1.25rem;
  width: 14rem;
}
.card-title {
  font-size: 2rem;
}
.card-content {
  display: flex;
  align-items: center;
}
img {
  width: 48px;
}
</style>
