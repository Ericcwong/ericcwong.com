<template>
  <section class="intro">
    <div class="header">
      <div class="header-top"></div>
      <!-- <div class="header-left"></div> -->
      <div class="sub-title-one">Hi, I'm</div>
      <div class="header-title">Eric</div>
      <div class="sub-title-two">a Web Developer</div>
      <div class="header-bottom"></div>
    </div>

    <div class="description">
      <p>Welcome to my portfolio!</p>
      <p>
        I develop websites using Nuxt and Vue. I am learning to improve my
        design and JavaScript skill.
      </p>
    </div>
  </section>
</template>

<script>
import HomePanel from "~/components/UI/Landing-Page/HomePanel.vue";
import GuySVG from "~/components/UI/SVG/GuySVG.vue";
import gsap from "gsap";
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
          name: "Github",
          to: "https://github.com/Ericcwong",
          class: "github",
        },
        {
          name: "LinkedIn",
          to: "/https://www.linkedin.com/in/eric-wong-b721bbb2/",
          class: "linkedin",
        },
      ],
    };
  },
  methods: {
    lineAnimation() {
      gsap.from(".header-top", 1, {
        scaleX: 0,
        transformOrigin: "right",
        opacity: 0,
        duration: 2,
        ease: "power4.out",
      });
      gsap.from(".header-left", {
        scaleY: 0,
        transformOrigin: "right top",
        opacity: 0,
        delay: 1,
        duration: 2,
        ease: "power4.out",
      });
      gsap.from(".header-bottom", 1, {
        scaleX: 0,
        transformOrigin: "left",
        opacity: 0,
        delay: 1.5,
        duration: 2,
        ease: "power4.out",
      });
    },
    titleAnimation() {
      gsap.from(".header-title", {
        x: -100,
        opacity: 0,
        duration: 2,
        delay: 1.4,
        ease: "power4.out",
      });
      // Sub title animation. (The "I am" ... "a Web developer")
      gsap.from(".sub-title-one", {
        x: -100,
        opacity: 0,
        duration: 1.5,
        delay: 1,
        ease: "power4.out",
      });
      gsap.from(".sub-title-two", {
        x: -100,
        opacity: 0,
        duration: 1.5,
        delay: 1.7,
        ease: "power4.out",
      });
    },
  },

  mounted() {
    this.titleAnimation();
    this.lineAnimation();
  },
};
</script>

<style scoped>
.intro {
  display: grid;
  height: 90vh;
  justify-content: center;
  align-items: center;
  color: white;
}
.header {
  display: grid;
  grid-template-areas:
    "header-top"
    "subTitleOne"
    "title"
    "subTitleTwo"
    "header-bottom";
}

.header-top {
  border-top: 2px solid white;
  grid-area: header-top;
  width: 100%;
}
.header-bottom {
  border-bottom: 2px solid white;
  grid-area: header-bottom;
}
.header-title {
  font-size: 6vw;
  grid-area: title;
}
.sub-title-one,
.sub-title-two {
  font-size: 4vw;
}
.sub-title-one {
  grid-area: subTitleOne;
}
.sub-title-two {
  grid-area: subTitleTwo;
}

.description {
  /* max-width: 50%; */
  font-size: 1.5rem;
  margin-top: -15rem;
}

@media only screen and (max-width: 1050px) {
  .header-title {
    font-size: 10vw;
    grid-area: title;
  }
  .sub-title-one,
  .sub-title-two {
    font-size: 10vw;
  }
}
</style>
