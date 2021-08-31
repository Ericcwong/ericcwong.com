<template>
  <section class="container">
    <div class="introduction">
      <div class="introduction-title">
        <span> Hello, there! </span>
        <span> My name is Eric</span>
        <span>A Fullstack developer</span>
      </div>
      <ul class="introduction-links">
        <li v-for="link in links" :key="link.name">
          <nuxt-link :to="link.to">{{ link.name }}</nuxt-link>
        </li>
      </ul>
    </div>
    <!-- <HomeSkills /> -->
    <!-- <HomeContent /> -->
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
  data() {
    return {
      links: [
        { name: "Projects", to: "/projects" },
        {
          name: "About",
          to: "/about",
        },
        {
          name: "Contact",
          to: "mailto:ericcwong12@gmail.com",
        },
      ],
    };
  },
};
</script>

<style scoped>
.container {
  display: grid;
  justify-content: center;
  align-items: center;
}
.introduction {
  display: grid;
  grid-template-columns: 70% 30%;
  color: white;
}
.introduction-title {
  display: inline;
  font-size: 4em;
}
.introduction-links > li {
  list-style: none;
  text-align: center;
  margin: 1em 0 1em 0;
  border: 1px solid whitesmoke;
}
.introduction-links > li > a {
  color: lightgray;
  font-size: 3em;
  text-decoration: none;
}
</style>
