<template>
  <!-- <TheHeader text="My Counter" /> -->
  <TheHeader
    v-bind:text="Math.floor(Math.random() * 10) % 2 === 0 ? 'even' : 'odd'"
  />
</template>

<script>
import TheHeader from "./components/TheHeader.vue";

export default {
  components: {
    TheHeader,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
