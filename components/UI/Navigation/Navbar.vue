<template>
  <nav>
    <div class="nav-left">
      <img src="@/components/UI/SVG/logo.png" alt="" />
      <ul class="nav-links">
        <li class="link" v-for="navLink in navLinks" :key="navLink.name">
          <nuxt-link :to="navLink.to">{{ navLink.name }}</nuxt-link>
        </li>
      </ul>
    </div>

    <ul class="nav-links">
      <li class="link" v-for="contact in contacts" :key="contact.name">
        <a :href="contact.to">{{ contact.name }}</a>
      </li>
    </ul>
  </nav>
</template>

<script>
export default {
  data() {
    return {
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
};
</script>

<style scoped>
nav,
.nav-left,
.nav-right,
.nav-links {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
img {
  width: 175px;
}
.nav-links {
  margin: 0 1.5rem 0 1.5rem;
  justify-content: space-between;
}

.link {
  list-style: none;
  margin: 0 1.5rem 0 1.5rem;
}
.link a {
  color: white;
  text-decoration: none;
}
</style>
