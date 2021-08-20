<template>
  <TheHeader text="My counter" />
  <div>{{ count }}</div>
  <BaseButton @onClick="minusOne">-</BaseButton>
  <BaseButton @onClick="plusOne">+</BaseButton>

  <NumberInput v-model.numberOnly="inputCount" />
  <BaseButton @onClick="insertCount">insert</BaseButton>
</template>

<script>
import TheHeader from "./components/TheHeader.vue";
import BaseButton from "./components/BaseButton.vue";
import NumberInput from "./components/NumberInput.vue";

export default {
  components: {
    TheHeader,
    BaseButton,
    NumberInput,
  },
  data() {
    return {
      count: 0,
      inputCount: 0,
    };
  },
  methods: {
    plusOne() {
      this.count++;
    },
    minusOne() {
      this.count--;
    },
    insertCount() {
      this.count = this.inputCount;
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
