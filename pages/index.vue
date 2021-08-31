<template>
  <section class="intro">
    <div class="intro-content">
      <p class="intro-sub-title">
        Building steps towards the future one step at a time
      </p>
      <ul class="intro-links">
        <li :class="link.class" v-for="link in links" :key="link.name">
          <nuxt-link :to="link.to">{{ link.name }}</nuxt-link>
        </li>
      </ul>
      <div class="intro-title">
        Hello, there! My name is Eric a Fullstack developer
      </div>
      <p class="see-more">See More</p>
    </div>
  </section>
</template>

<script>
import HomePanel from "~/components/UI/Landing-Page/HomePanel.vue";

export default {
  components: {
    HomePanel,
  },
  data() {
    return {
      links: [
        { name: "Projects", to: "/projects", class: "projects" },
        {
          name: "About",
          to: "/about",
          class: "about",
        },
        {
          name: "Contact",
          to: "mailto:ericcwong12@gmail.com",
          class: "contact",
        },
      ],
    };
  },
};
</script>

<style scoped>
.intro {
  width: 100%;
  display: grid;
  justify-content: center;
  align-items: center;
  height: 100vh;
  position: relative;
}
/* Background image with blur effect */
.intro::before {
  content: " ";
  position: absolute;
  width: 100%;
  height: 100%;
  opacity: 0.12;
  background-image: url("/images/background.jpg");
  background-repeat: no-repeat;
  background-position: 50% 0;
  background-size: cover;
}

.intro-content {
  display: grid;
  grid-template-columns: 70% 30%;
  color: white;
}
.intro-sub-title {
  font-size: 2rem;
}
.intro-title {
  font-size: 3em;
}
.intro-links {
  display: grid;
}
.intro-links > li {
  list-style: none;
  margin: 1em 0 1em 0;
}
.intro-links > li > a {
  color: lightgray;
  font-size: 1.5rem;
  text-decoration: none;
}
.projects {
  text-align: left;
}
.about {
  text-align: center;
}
.contact {
  text-align: right;
}
.see-more {
}
</style>
