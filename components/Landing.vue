<template>
  <div class="animated-title">
    <div class="text-top">
      <div>
        <span>Eric Wong</span>
        <span>Web developer</span>
      </div>
    </div>
    <div class="text-bottom">
      <div>
        <p>Come on, Lets go!</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {};
</script>


<style scoped>
/* Breaking down the animations styling */
.animated-title {
  display: flex;
  justify-content: center;
  align-items: center;
  color: #222;
  font-family: Roboto, Arial, sans-serif;
  height: 100vh;
  /* left: 50%; */
  /* position: absolute; */
  /* top: 50%; */
  /* transform: translate(-50%, -50%); */
  /* width: 90vmin; */
}

/* Hides the text before revealing */
.animated-title > div {
  height: 50%;
  overflow: hidden;
  position: absolute;
  width: 100%;
}
/* Text sizing */
.animated-title > div div {
  font-size: 12vmin;
  padding: 2vmin 0;
  position: absolute;
}
/* Each line will be their own */
.animated-title > div div span {
  display: block;
}
/* Animation bar */
.animated-title > div.text-top {
  border-bottom: 1vmin solid rgb(51, 51, 51);
  top: 0;
}
.animated-title > div.text-top div {
  animation: showTopText 1s;
  animation-delay: 0.5s;
  animation-fill-mode: forwards;
  bottom: 0;
  transform: translate(0, 100%);
}
.animated-title > div.text-top div span:first-child {
  color: #000000;
}
.animated-title > div.text-bottom {
  bottom: 0;
}
.animated-title > div.text-bottom div {
  animation: showBottomText 0.5s;
  animation-delay: 1.75s;
  animation-fill-mode: forwards;
  top: 0;
  transform: translate(0, -100%);
}
.animated-title > div div p {
  font-size: 6vmin;
}
/* Text Animation */
@keyframes showTopText {
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
@keyframes showBottomText {
  0% {
    transform: translate3d(0, -100%, 0);
  }
  100% {
    transform: translate3d(0, 0, 0);
  }
}
</style>
