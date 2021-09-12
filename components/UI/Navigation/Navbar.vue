<template>
  <nav>
    <ul class="nav-left">
      <li><nuxt-link to="/" class="nav-title">Eric Wong</nuxt-link></li>
    </ul>
    <ul class="nav-center"></ul>
    <ul class="nav-right">
      <li v-for="navLink in navLinks" :key="navLink.name">
        <nuxt-link :to="navLink.to">{{ navLink.name }}</nuxt-link>
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
        { name: "Contact", to: "/contact" },
      ],
    };
  },
};
</script>

<style scoped>
nav {
  margin-top: 1.25rem;
  display: flex;
  align-items: center;
  justify-content: space-between;
}
.nav-left {
  flex: 1;

  text-align: center;
}
.nav-center {
  flex: 4 1 0;
}
.nav-right {
  display: flex;
  flex: 2;
  justify-content: space-evenly;
}
.nav-title {
  font-size: 2rem;
}
li {
  color: white;
  list-style: none;
}
a {
  text-decoration: none;
  color: white;
}
</style>
