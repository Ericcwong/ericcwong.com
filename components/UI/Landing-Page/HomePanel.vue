<template>
  <section class="intro">
    <div class="header">
      <div class="header-top"></div>
      <div class="header-left"></div>
      <div class="sub-title-one">I am</div>
      <div class="header-title">Eric</div>
      <div class="sub-title-two">a Web Developer</div>
      <div class="header-bottom"></div>
    </div>
    <div class="links">
      <a
        v-for="link in links"
        :key="link.name"
        :class="link.class"
        :href="link.to"
        >{{ link.name }}
      </a>
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
      const gsap = this.$gsap;
      gsap.from(".header-top", 1, {
        scaleX: 0,
        transformOrigin: "right",
        opacity: 0,
        duration: 2,
        ease: "power4.out",
      });
      gsap.from(".header-left", 1, {
        height: 0,
        opacity: 0,
        delay: 1,
        duration: 2,
        ease: "power4.out",
      });
      gsap.from(".header-bottom", 1, {
        width: 0,
        opacity: 0,
        delay: 1.5,
        duration: 2,
        ease: "power4.out",
      });
    },
    titleAnimation() {
      const gsap = this.$gsap;
      gsap.from(".header-title", {
        x: -100,
        opacity: 0,
        duration: 2,
        delay: 1.4,
        ease: "power4.out",
      });
      // Sub title animation. (The "I am" ... "a Fullstack developer")
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
        delay: 2,
        ease: "power4.out",
      });
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
      // Github Link
      gsap.from(".github", {
        opacity: 0,
        duration: 2,
        delay: 1.25,
        ease: "Power2.easeInOut",
      });
      // LinkedIn Link
      gsap.from(".linkedin", {
        opacity: 0,
        duration: 2,
        delay: 1.5,
        ease: "Power2.easeInOut",
      });
    },
  },

  mounted() {
    this.linkAnimation();
    this.titleAnimation();
    this.lineAnimation();
  },
};
</script>

<style scoped>
.intro {
  display: grid;
  height: 100vh;
  justify-content: center;
  align-items: center;
  position: relative;
  z-index: 1;
  color: white;
}
.header {
  display: grid;
  grid-template-areas:
    "header-left header-top"
    "header-left subTitleOne"
    "header-left title"
    "header-left subTitleTwo"
    "header-left header-bottom";
  margin-top: 4rem;
}
.header-left {
  border-left: 2px solid white;
  grid-area: header-left;
}
.header-top {
  border-top: 2px solid white;
  grid-area: header-top;
  width: 100%;
}
.header-bottom {
  border-bottom: 2px solid white;
  grid-area: header-bottom;
  width: 100%;
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
.links {
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
}
.links > a {
  color: lightgray;
  font-size: 1.5rem;
  text-decoration: none;
  position: relative;
}
a:hover {
  color: #fff;
}
a:after {
  content: "";
  position: absolute;
  width: 100%;
  transform: scaleX(0);
  height: 2px;
  bottom: 0;
  left: 0;
  background-color: #fff;
  transform-origin: bottom right;
  transition: transform 0.25s ease-out;
}
a:hover:after {
  transform: scaleX(1);
  transform-origin: bottom left;
}
/* .see-more {
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
  animation: arrowAnimation 1s linear infinite;
}
.arrow-indicator .arrow:nth-child(1) {
  top: 7.5px;
  left: 7.5px;
  animation-delay: 0.2s;
}
@keyframes arrowAnimation {
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
} */

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
