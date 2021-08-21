<template>
  <TheHeader text="My counter" />
  <div v-if="!validationMessageList.length">{{ count }}</div>
  <div v-else v-for="message in validationMessageList" :key="message">
    {{ message }}
  </div>
  <BaseButton :disabled="hasMinCount" @onClick="minusOne">-</BaseButton>
  <BaseButton :disabled="hasMaxCount" @onClick="plusOne">+</BaseButton>

  <NumberInput v-model.numberOnly="inputCount" />
  <BaseButton
    :disabled="hasMinInputCount || hasMaxInputCount"
    @onClick="insertCount"
    >insert</BaseButton
  >
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
      isEditing: false,
    };
  },
  methods: {
    plusOne() {
      this.inputCount++;
    },
    minusOne() {
      this.inputCount--;
    },
    insertCount() {
      if (this.hasMaxInputCount || this.hasMinInputCount) {
        return;
      }
      this.count = this.inputCount;
      this.isEditing = false;
      alert("編集完了!!");
    },
  },
  watch: {
    inputCount() {
      this.isEditing = true;
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
    // 入力した数字が9999を超えたらtrueを返す
    hasMaxInputCount() {
      return this.inputCount > 9999;
    },
    // 入力した数字が0を下回ったらtrueを返す
    hasMinInputCount() {
      return this.inputCount < 0;
    },
    validationMessageList() {
      const validationList = [];

      if (this.isEditing) {
        validationList.push("編集中...");
      }

      if (this.hasMaxInputCount) {
        validationList.push("9,999以下の数字を入力してください");
      }

      if (this.hasMinInputCount) {
        validationList.push("0以上の数字を入力してください");
      }
      return validationList;
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
