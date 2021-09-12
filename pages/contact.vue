<template>
  <div class="container">
    <form>
      <label for="email">Email</label>
      <input type="email" id="email" v-model="email" />
    </form>
  </div>
</template>

<script>
export default {};
</script>

<style scoped>
.container {
  background-color: #ffffff;
  background-image: linear-gradient(315deg, #ffffff 0%, #d7e1ec 74%);
  display: flex;
  justify-content: center;
  align-items: center;
}
input {
  border: 1px solid black;
  border-radius: 1.5rem;
}
</style>