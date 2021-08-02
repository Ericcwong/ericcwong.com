<template>
  <section class="pannels">
    <div class="pannel" v-for="pannel in pannels" :key="pannel.name">
      <img class="pannel-image" :src="pannel.image" :alt="pannel.alt" />
      <span class="pannel-name">{{ pannel.name }}</span>
    </div>
  </section>
</template>

<script>
import { reactive } from "@nuxtjs/composition-api";
import projectsSVG from "~/components/UI/SVG/projects.svg";
export default {
  data() {
    return {
      pannels: [
        {
          name: "Project",
          image: projectsSVG,
          alt: "Website building drawing",
        },
        {
          name: "Github",
        },
        {
          name: "Contact",
        },
      ],
    };
  },
};
</script>

<style scoped>
.pannels {
  background-color: lightgray;
  height: 50vh;
  display: flex;
  justify-content: space-around;
}
.pannel {
  display: inline-grid;
}

.pannel-image {
  width: 50%;
}
</style>