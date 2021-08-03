<template>
  <nav>
    <v-app-bar dark>
      <v-toolbar-title><nuxt-link to="/">Eric Wong</nuxt-link></v-toolbar-title>

      <v-spacer></v-spacer>
      <v-app-bar-nav-icon class="nav-drawer" @click.stop="drawer = !drawer">
      </v-app-bar-nav-icon>
      <div class="pages">
        <nuxt-link
          class="page"
          :to="page.redirect"
          icon
          v-for="page in pages"
          :key="page.name"
        >
          <span>{{ page.name }}</span>
        </nuxt-link>
      </div>
    </v-app-bar>

    <v-navigation-drawer v-model="drawer" absolute bottom temporary>
      <v-list nav dense>
        <v-list-item-group
          v-model="group"
          active-class="deep-purple--text text--accent-4"
        >
          <v-list-item>
            <v-list-item-title>Foo</v-list-item-title>
          </v-list-item>

          <v-list-item>
            <v-list-item-title>Bar</v-list-item-title>
          </v-list-item>

          <v-list-item>
            <v-list-item-title>Fizz</v-list-item-title>
          </v-list-item>

          <v-list-item>
            <v-list-item-title>Buzz</v-list-item-title>
          </v-list-item>
        </v-list-item-group>
      </v-list>
    </v-navigation-drawer>
  </nav>
</template>

<script>
export default {
  data() {
    return {
      drawer: false,
      group: null,
      pages: [
        { name: "Home", redirect: "/" },
        { name: "Projects", redirect: "/projects" },
        { name: "About me", redirect: "/about" },
      ],
    };
  },
  watch: {
    group() {
      this.drawer = false;
    },
  },
};
</script>

<style scoped>
a {
  text-decoration: none;
  color: white;
}
.nav-drawer {
  display: none;
}
.page {
  margin: 0 1.25rem 0 1.25rem;
}
@media only screen and (max-width: 880px) {
  .nav-drawer {
    display: block;
  }
  .pages {
    display: none;
  }
}
</style>