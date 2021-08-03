<template>
  <section class="projects">
    <span class="title">Projects I developed</span>
    <v-card
      class="mx-auto"
      :id="project.name"
      max-width="344"
      v-for="project in projects"
      :key="project.name"
    >
      <v-img :src="project.image" height="200px"></v-img>
      <v-card-title> {{ project.name }} </v-card-title>
      <v-card-subtitle> {{ project.shortDescription }} </v-card-subtitle>
      <v-card-actions>
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
      </v-expand-transition>
    </v-card>
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
.projects {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
}
.title {
  flex: 0 0 100%;
  margin-bottom: 2rem;
  font-size: 1.25rem;
}
.project-image {
  width: 40%;
}
</style>
