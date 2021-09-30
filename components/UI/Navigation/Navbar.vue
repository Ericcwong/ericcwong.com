<template>
  <nav>
    <img src="@/components/UI/SVG/logo.png" alt="" />
    <div class="nav-left">
      <ul class="nav-links" :class="{ active: isActive }">
        <li class="link" v-for="navLink in navLinks" :key="navLink.name">
          <button @click="hamburger()" class="nav-button">
            <nuxt-link :to="navLink.to">{{ navLink.name }}</nuxt-link>
          </button>
        </li>
      </ul>
    </div>
    <div class="nav-right">
      <ul class="nav-links" :class="{ active: isActive }">
        <li class="link" v-for="contact in contacts" :key="contact.name">
          <button @click="hamburger()" class="nav-button">
            <nuxt-link :to="contact.to">{{ contact.name }}</nuxt-link>
          </button>
        </li>
      </ul>
    </div>
    <button
      class="hamburger"
      :class="{ active: isActive }"
      @click="hamburger()"
    >
      <span></span>
      <span></span>
      <span></span>
    </button>
  </nav>
</template>

<script>
export default {
  data() {
    return {
      isActive: false,
      navLinks: [
        { name: "Home", to: "/" },
        { name: "Project", to: "/project" },
        { name: "About", to: "/about" },
      ],
      contacts: [
        { name: "Contact", to: "/contact" },
        { name: "Github", to: "https://www.github.com/ericcwong" },
        {
          name: "LinkedIn",
          to: "https://www.linkedin.com/in/eric-wong-b721bbb2/",
        },
      ],
    };
  },
  methods: {
    hamburger() {
      this.isActive = !this.isActive;
    },
  },
};
</script>

<style scoped>
.nav-bar {
  position: sticky;
  top: 0;
  width: 100%;
  z-index: 100;
}
nav,
.nav-left,
.nav-right,
.nav-links {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
img {
  width: 100px;
}
.nav-links {
  margin: 0 1.5rem 0 1.5rem;
  justify-content: space-between;
}

.link {
  list-style: none;
  margin: 0 1.5rem 0 1.5rem;
}

a {
  position: relative;
  color: #000;
  text-decoration: none;
  color: white;
  text-decoration: none;
}

a::before {
  content: "";
  position: absolute;
  display: block;
  width: 100%;
  height: 2px;
  bottom: 0;
  left: 0;
  background-color: #fff;
  transform: scaleX(0);
  transform-origin: bottom left;
  transition: transform 0.3s ease;
}

a:hover::before {
  transform: scaleX(1);
}
.nav-button {
  font-size: 1rem;
  font-family: "Spartan", sans-serif;
  user-select: none;
  appearance: none;
  border: none;
  outline: none;
  background: none;
}
/* Hamburger for mobile view */
.hamburger {
  display: none;
  position: absolute;
  right: 1rem;
  top: 2rem;
  z-index: 1;
  cursor: pointer;
  user-select: none;
  appearance: none;
  border: none;
  outline: none;
  background: none;
}
.hamburger span {
  display: block;
  width: 33px;
  height: 4px;
  margin-bottom: 5px;
  margin-right: 1.5rem;
  position: relative;
  border-radius: 6px;
  z-index: 1;
  transform-origin: 0 0;
  transition: 0.4s;
  background: white;
}
.hamburger.active span:nth-child(1) {
  transform: translate(0px, -2px) rotate(45deg);
}
.hamburger:hover span:nth-child(2) {
  transform: translateX(10px);
}

.hamburger.active span:nth-child(2) {
  opacity: 0;
  transform: translateX(15px);
}
.hamburger.active span:nth-child(3) {
  transform: translate(-3px, 3px) rotate(-45deg);
}
.hamburger.active:hover span {
  background: rgb(163, 53, 53);
}
/* End of hamburger */
@media (max-width: 1050px) {
  nav {
    flex-direction: column;
  }

  .nav-links {
    display: none;
  }
  .nav-links.active {
    display: flex;
    flex-direction: column;
    width: 100vw;
    animation: growDown 700ms ease-in-out forwards;
    transform-origin: top center;
  }
  .nav-links.active li {
    height: 3rem;
    display: flex;
    align-items: center;
  }

  .hamburger {
    display: block;
  }
}
@keyframes growDown {
  0% {
    /* transform: translateY(-100%); */
    opacity: 0;
  }
  /* 80% {
    transform: scaleY(1.1);
  } */
  100% {
    /* transform: translateY(0); */
    opacity: 1;
  }
}
</style>
