<template>
  <section class="projects">
    <span class="title">Projects I developed</span>
    <div class="project-cards">
      <div
        class="project-card mx-auto"
        :id="project.name"
        v-for="project in projects"
        :key="project.name"
      >
        <img :src="project.image" />
        <span> {{ project.name }} </span>
        <span> {{ project.shortDescription }} </span>
        <!-- <v-card-actions>
          <v-btn color="orange lighten-2" text> More Information </v-btn>
          <v-spacer></v-spacer>
          <v-btn icon @click="show = !show">
            <v-icon>{{ show ? "mdi-chevron-up" : "mdi-chevron-down" }}</v-icon>
          </v-btn>
        </v-card-actions>
        <v-expand-transition>
          <div v-show="show">
            <v-divider></v-divider>
            <v-card-text>
              {{ project.description }}
            </v-card-text>
          </div>
        </v-expand-transition> -->
      </div>
    </div>
  </section>
</template>

<script>
export default {
  computed: {
    projects() {
      return this.$store.state.projects;
    },
  },
  data() {
    return {
      show: false,
    };
  },
};
</script>

<style scoped>
/* .projects {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
} */
.title {
  font-size: 2em;
}
.project-cards {
  display: grid;
  grid-template-columns: repeat(3, auto);
}
.project-card {
  display: grid;
}
img {
  max-width: 100%;
}
</style>
