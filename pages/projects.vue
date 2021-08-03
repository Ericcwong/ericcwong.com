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
  data() {
    return {
      projects: [
        {
          name: "Crypto Market",
          image:
            "https://lh3.googleusercontent.com/Lk_5dJKpKsSY32kyQhI3ZVHdNs9vlbNUkPYHLguQXFkyFPjXiPByoBH9fZjDWUSve7zDjmP1T0FNHCzd1ZbxTB7NmQQXHjSlZiZUf3_GiZhrkVGO3KCpESLyZb1f-Vzrky6SrhHRDA=w2400",
          description: "",
          deployLink:
            "https://ericcwong-crypto-market.herokuapp.com/pancakeswap-token",
          githubLink: "https://github.com/Ericcwong/Crypto-Market",
        },
        {
          name: "Blog",
          image: "",
          deployLink: "https://ericcwong-blog.herokuapp.com/",
          githubLink: "https://github.com/Ericcwong/Blog",
        },
      ],
    };
  },
};
</script>

<style></style>
