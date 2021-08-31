<template>
  <section class="icons">
    <div class="arrow-up"></div>
    <div class="vertical-line"></div>
    <div class="icon" v-for="social in socials" :key="social.name">
      <a :href="social.link" target="_blank">
        <img :src="social.icon" alt="" />
      </a>
    </div>
    <div class="vertical-line"></div>
    <div class="arrow-down"></div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      socials: [
        {
          name: "Email",
          icon: "https://image.flaticon.com/icons/png/512/893/893257.png",
          link: "mailto:ericcwong12@gmail.com",
        },
        {
          name: "Phone",
          icon: "https://image.flaticon.com/icons/png/512/684/684911.png",
          link: "tel:8019318459",
        },
        {
          name: "Github",
          icon: "https://image.flaticon.com/icons/png/512/270/270798.png",
          link: "https://github.com/ericcwong",
        },
        {
          name: "LinkedIn",
          icon: "https://image.flaticon.com/icons/png/512/174/174857.png",
          link: "https://www.linkedin.com/in/eric-wong-b721bbb2/",
        },
      ],
    };
  },
};
</script>

<style scoped>
.icons {
  justify-content: center;
  align-items: center;
  text-align: center;
  position: fixed;
}
.arrow-up {
  margin: auto;
  width: 1.5em;
  height: 1.5em;
  border-top: 0.25em solid #fff;
  border-right: 0.25em solid #fff;
  -moz-transform: rotate(-45deg);
  -webkit-transform: rotate(-45deg);
  transform: rotate(-45deg);
}
.arrow-down {
  margin: auto;
  width: 1.5em;
  height: 1.5em;
  border-top: 0.25em solid #fff;
  border-right: 0.25em solid #fff;
  -moz-transform: rotate(-45deg);
  -webkit-transform: rotate(-45deg);
  transform: rotate(135deg);
}
.vertical-line {
  display: inline-block;
  border-left: 0.1em solid #fff;
  margin: 0 10px;
  height: 50px;
}
img {
  margin: 4px 0 4px 0;
  max-width: 5rem;
  width: 50%;
}
</style>
