<template>
  <TheHeader
    v-bind:text="Math.floor(Math.random() * 10) % 2 === 0 ? 'even' : 'odd'"
  />
  <BaseButton @onClick="alertOnClick">+</BaseButton>
</template>

<script>
import TheHeader from "./components/TheHeader.vue";
import BaseButton from "./components/BaseButton.vue";

export default {
  components: {
    TheHeader,
    BaseButton,
  },
  methods: {
    alertOnClick() {
      alert("Button Clicked!!!");
    },
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
