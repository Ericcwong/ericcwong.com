<template>
  <section class="landing-home">
    <div class="landing-container">
      <div class="landing-title-top">
        <span>Eric Wong</span>
        <span>Web Developer</span>
      </div>
      <div class="landing-title-bottom">
        <span>Come on, Lets go!</span>
      </div>
    </div>
  </section>
</template>

<script>
export default {};
</script>

<style scoped>
/* Landing component */
.landing-home {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
}
/* Center content  */
.landing-container {
  display: grid;
  grid-template-columns: 1fr;
  justify-content: center;
  align-items: center;
}
/* Top of the center content */
.landing-title-top {
  display: grid;
  grid-template-columns: 1fr;
  border-bottom: 8px solid black;
  font-size: 3rem;
}
.landing-title-top > span {
  animation: 1s ease-out 0s 1 slideInFromLeft;
  animation-delay: 0.05s;
  animation-fill-mode: forwards;
}

/* Animations */
@keyframes slideInFromLeft {
  0% {
    transform: translate3d(0, 100%, 0);
  }
  40%,
  60% {
    transform: translate3d(0, 50%, 0);
  }
  100% {
    transform: translate3d(0, 0, 0);
  }
}
</style>
