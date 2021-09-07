<template>
  <section class="intro">
    <div class="content">
      <div>
        <div class="sub-title">I am</div>
        <div class="title">Eric</div>
        <div class="sub-title">an Fullstack developer</div>
      </div>
      <GuySVG class="SVG" />
      <p class="sub-title">
        Building steps towards the future one step at a time
      </p>
      <div class="links">
        <nuxt-link
          v-for="link in links"
          :key="link.name"
          :class="link.class"
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
import GuySVG from "~/components/UI/SVG/GuySVG.vue";
export default {
  components: {
    HomePanel,
    GuySVG,
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
  methods: {
    // Sub title animation
    subTitleAnimation() {
      const gsap = this.$gsap;
      gsap.from(".sub-title", {
        y: -100,
        opacity: 0,
        duration: 1.5,
        ease: "Power2.easeInOut",
      });
      gsap.to(".sub-title", { duration: 1, delay: 1 });
    },
    //Link animations
    linkAnimation() {
      const gsap = this.$gsap;
      // Project Link
      gsap.from(".projects", {
        opacity: 0,
        duration: 2,
        delay: 1,
        ease: "Power2.easeInOut",
      });
      gsap.to(".projects", { x: 0, duration: 1, delay: 1 });
      // About Link
      gsap.from(".about", {
        opacity: 0,
        duration: 2,
        delay: 1.25,
        ease: "Power2.easeInOut",
      });
      gsap.to(".about", { x: 0, duration: 1, delay: 1.25 });
      // Contact Link
      gsap.from(".contact", {
        opacity: 0,
        duration: 2,
        delay: 1.5,
        ease: "Power2.easeInOut",
      });
      gsap.to(".contact", { x: 0, duration: 1, delay: 1.5 });
    },
    titleAnimation() {
      const gsap = this.$gsap;
      gsap.from(".title", {
        duration: 2,
        ease: "SteppedEase.config(20)",
      });
    },
  },

  mounted() {
    this.subTitleAnimation();
    this.linkAnimation();
    this.titleAnimation();
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
  background-color: #000000;
  background-image: linear-gradient(147deg, #000000 0%, #2c3e50 74%);
  z-index: 1;
}
/* Background image with blur effect */
.intro:before {
  content: " ";
  position: absolute;
  width: 100%;
  height: 100%;
  opacity: 0.12;

  z-index: -1;
}

.content {
  display: grid;
  height: 50vh;
  margin: 10rem;
  padding: 4rem;
  grid-template-columns: 1fr 1fr 1.5fr;
  grid-template-rows: 70% 30%;
  column-gap: 5rem;
  row-gap: 2.5rem;
  grid-template-areas:
    "title title SVG"
    "subTitle subTitle links";
  color: white;
}
.title {
  font-size: 3em;
  grid-area: title;
}
.sub-title {
  font-size: 1.75rem;
  grid-area: subTitle;
}
.links {
  display: grid;
  column-gap: 5rem;
  grid-template-columns: fit-content(100%) fit-content(100%) fit-content(100%);
  grid-template-areas:
    "project . ."
    ". about. "
    ". . contact";
  grid-area: links;
}
a:nth-child(1) {
  text-align: left;
}
.links > a {
  color: lightgray;
  font-size: 1.5rem;
  text-decoration: none;
  position: relative;
  /* width: 100%; */
  overflow: hidden; /* NEW */
  min-width: 0; /* NEW; needed for Firefox */
}
a:hover {
  color: #fff;
}
a::before {
  content: "";
  position: absolute;
  display: block;
  width: 100%;
  height: 2px;
  bottom: 0;
  left: 0;
  background-color: #000;
  transform: scaleX(0);
  transition: transform 0.3s ease;
}
a:hover::before {
  transform: scaleX(1);
}
.projects {
  grid-area: project;
}
.about {
  grid-area: about;
}
.contact {
  grid-area: contact;
}
.see-more {
  display: flex;
  font-size: 1.5rem;
  color: white;
  justify-content: center;
  align-self: flex-end;
}
span {
  font-size: 30px;
}
.SVG {
  object-fit: contain;
  max-height: 100%;
  width: 100%;
  grid-area: SVG;
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

@media only screen and (max-width: 1050px) {
  .intro:before {
    content: " ";
    position: absolute;
    width: 100%;
    height: 100%;
    opacity: 0.12;
    background-image: url("/images/background.jpg");
    background-repeat: no-repeat;
    background-size: cover;
    background-position: center;
    z-index: -1;
  }
  .content {
    display: grid;
    grid-template-areas:
      "title title"
      "subTitle subTitle"
      "links links";
    grid-template-rows: auto;
    margin: 2rem;
    font-size: 12px;
    height: 70vh;
  }
  .sub-title {
    margin: 2rem 0 2rem 0;
  }
  .links {
    margin: 2rem 0 2rem 0;
  }
  .see-more {
    align-self: flex-end;
  }
}
</style>