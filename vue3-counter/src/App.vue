<template>
  <TheHeader text="My counter" />
  <div>{{ count }}</div>
  <BaseButton :disabled="hasMinCount" @onClick="minusOne">-</BaseButton>
  <BaseButton :disabled="hasMaxCount" @onClick="plusOne">+</BaseButton>

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
  watch: {
    inputCount(value) {
      if (value >= 9999) {
        this.count = 9999;
      }
      if (value <= 0) {
        this.count = 0;
      }
    },
  },
  computed: {
    // countが9999を超えたらtrueを返す
    hasMaxCount() {
      return this.count >= 9999;
    },
    // countが0を下回ったらtrueを返す
    hasMinCount() {
      return this.count <= 0;
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
