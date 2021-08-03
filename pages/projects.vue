<template>
  <section class="container">
    <v-card v-for="project in projects" :key="project.name">
      <v-img width="55rem" :src="project.image"></v-img>
      <v-card-title> {{ project.name }} </v-card-title>
      <v-card-actions>
        <a :href="project.deployLink" target="_blank">Deploy</a>
      </v-card-actions>
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
    return {};
  },
};
</script>

<style></style>
