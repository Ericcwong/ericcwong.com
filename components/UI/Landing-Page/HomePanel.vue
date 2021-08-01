<template>
  <section class="panel">
    <div class="contents">
      <div v-for="content in contents" :key="content.name">
        {{ content.name }}
      </div>
    </div>
  </section>
</template>

<script>
import { reactive } from "@nuxtjs/composition-api";
export default {
  data() {
    return {
      contents: [
        {
          name: "Project",
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
  //   setup() {
  //     const state = reactive({
  //       contents: [{}],
  //     });
  //     return { state };
  //   },
};
</script>

<style>
</style>