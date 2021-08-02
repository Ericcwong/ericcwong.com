<template>
  <section class="container">
    <v-cards v-for="project in projects" :key="project.name">
      <v-img width="55rem" :src="project.image"></v-img>
      <v-card-title> {{ project.name }} </v-card-title>
      <v-card-actions>
        <a :href="project.deployLink" target="_blank">Deploy</a>
      </v-card-actions>
    </v-cards>
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
            "https://lh3.googleusercontent.com/N5EB4c_fdOX6l2aTbMCiFr8xyPZfLwoGrRFWWzIbO43ZHrxY4-tN7u7tjXQnaGykeEY4qr42IsPaytqbFPhQ-WRSiSvVjlA0jmK8Z7Q_W5mmKMU9U7n1MPemmsosxquI6ZGAu6nBhyi6JW3hya9GMdBb4vFIZnQWqeN6ipgabcL6LM9asJg1isBwUmyRb0L0ls4lNYcn3iqb3tj5CHCRrdmjPOYG9WulhXnkxNaAghV3t6DnytpgRAcwU8vxU3PBILycelus5L8pkw-Rylpg9JC_Q1O8vI7m8W2TTpXaenW8Acn89fAVNQHz-zyPAG5TaXSYfKxQ8-loh_JralcbXkYqzKKR2cm4mOKqjYsMx0awfpZoQB9i3GiPl2pGVWrfR1lwz_mAbpyIC_tupmgXgRdX4j_BCRNWF8zYo0W7ZvpPxV0vSRSU99SnHuxPMDee-2_vGhHmxCeZi06DzTiuMwnuUMD8MwfVDieQNszJ27oyTKx4xGxOx59ow4rR39AKPVj6mOUWM125q2e3fgHrshMOjSplo3WakqNYrCeJLuotsNmbKFH8IVQknNmIRtwJswZiQjKmOlqizxBpFbAMzgTWzq0hVIZA4WD5-aptgy7MutfwUmKDQYdaGIgOBibChgW-grxzQfBS8zTGVVcKQiKq_m4-MhE9cnCcEOSLz5qYuo9XTZXEqT84vXdmOV-xuxGCn0eTJICAQk7otH5hAnVI=w1440-h734-no?authuser=0",
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

<style>
</style>