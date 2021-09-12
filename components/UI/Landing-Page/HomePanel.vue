<template>
  <section class="intro">
    <div class="header">
      <div class="header-top"></div>
      <div class="header-left"></div>
      <div class="sub-title-one">I am</div>
      <div class="title">Eric</div>
      <div class="sub-title-two">a Fullstack developer</div>
      <div class="header-bottom"></div>
    </div>
    <div class="links">
      <nuxt-link
        v-for="link in links"
        :key="link.name"
        :class="link.class"
        :to="link.to"
        >{{ link.name }}
      </nuxt-link>
    </div>

    <div class="see-more">
      <p>Lets dive deeper</p>
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
          to: "/contact",
          class: "contact",
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
        duration: 2,
        delay: 1.5,
        ease: "power4.out",
      });
    },
    titleAnimation() {
      const gsap = this.$gsap;
      gsap.from(".title", {
        x: -100,
        opacity: 0,
        duration: 2,
        delay: 1.4,
        ease: "power4.out",
      });
    },

    // Sub title animation
    subTitleAnimation() {
      const gsap = this.$gsap;
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
      // About Link
      gsap.from(".about", {
        opacity: 0,
        duration: 2,
        delay: 1.25,
        ease: "Power2.easeInOut",
      });
      // Contact Link
      gsap.from(".contact", {
        opacity: 0,
        duration: 2,
        delay: 1.5,
        ease: "Power2.easeInOut",
      });
    },
  },

  mounted() {
    this.subTitleAnimation();
    this.linkAnimation();
    this.titleAnimation();
    this.lineAnimation();
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
}
.header-left {
  border-left: 2px solid white;
  grid-area: header-left;
}
.header-top {
  border-top: 2px solid white;
  grid-area: header-top;
}
.header-bottom {
  border-bottom: 2px solid white;
  grid-area: header-bottom;
}
.title {
  font-size: 6em;
  grid-area: title;
}
.sub-title-one,
.sub-title-two {
  font-size: 4rem;
}
.sub-title-one {
  grid-area: subTitleOne;
}
.sub-title-two {
  grid-area: subTitleTwo;
}
a::nth-child(1) {
  text-align: left;
}
.links {
  display: flex;
  justify-content: space-between;
}
.links > a {
  color: lightgray;
  font-size: 1.5rem;
  text-decoration: none;
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
}

@media only screen and (max-width: 1050px) {
}
</style>