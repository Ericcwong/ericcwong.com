<template>
  <section class="intro">
    <div class="intro-content">
      <div class="intro-title">
        Hello, there! My name is Eric a Fullstack developer
      </div>
      <p class="intro-sub-title">
        Building steps towards the future one step at a time
      </p>
      <div class="intro-links">
        <nuxt-link
          :class="link.class"
          v-for="link in links"
          :key="link.name"
          :to="link.to"
          >{{ link.name }}
        </nuxt-link>
      </div>
    </div>
    <div class="see-more">
      <p>See More</p>
      <div class="arrow-indicator">
        <span class="arrow"></span>
        <span class="arrow"></span>
        <span class="arrow"></span>
      </div>
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
  display: grid;
  justify-content: center;
  align-items: center;
  height: 100vh;
  position: relative;
  z-index: 1;
}
/* Background image with blur effect */
.intro:before {
  content: " ";
  position: absolute;
  width: 100%;
  height: 100%;
  opacity: 0.12;
  background-image: url("/images/background.jpg");
  background-repeat: no-repeat;
  background-size: cover;
  z-index: -1;
}

.intro-content {
  display: grid;
  height: 50vh;
  grid-template-areas:
    "title title title title"
    "subTitle subTitle links links";
  grid-template-rows: auto;
  color: white;
}
.intro-title {
  font-size: 3em;
  grid-area: title;
}
.intro-sub-title {
  font-size: 1.75rem;
  grid-area: subTitle;
}
.intro-links {
  display: grid;
  grid-area: links;
}
.intro-links > a {
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
  display: flex;
  font-size: 1.5rem;
  color: white;
  justify-content: center;
}
span {
  font-size: 30px;
}

svg.baseline {
  width: 100%;
}

svg.baseline line {
  stroke: red;
  stroke-width: 0.06;
}
.arrow-indicator {
  position: relative;
  width: 50px;
  height: 50px;
  transform: rotate(45deg);
}
.arrow-indicator .arrow {
  position: absolute;
  top: 0;
  left: 0;
  width: 20px;
  height: 20px;
  display: block;
  box-sizing: border-box;
  border: none;
  border-bottom: 3px solid #fff;
  border-right: 3px solid #fff;
  animation: animate 1s linear infinite;
}
.arrow-indicator .arrow:nth-child(1) {
  top: 7.5px;
  left: 7.5px;
  animation-delay: 0.2s;
}
@keyframes animate {
  0% {
    border-color: #fff;
  }
  20% {
    border-color: #fff;
  }
  20.1%,
  100% {
    border-color: #222;
  }
}
</style>
