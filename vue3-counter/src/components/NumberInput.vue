<template name="component-name">
  <input :value="modelValue" @input="emitValue" type="number" />
</template>

<script>
export default {
  name: "NumberInput",
  emits: ["update:modelValue"],
  props: {
    modelValue: {
      type: Number,
      default: 0,
    },
    modelModifiers: {
      default: () => ({}),
    },
  },
  methods: {
    emitValue({ target: { value } }) {
      if (this.modelModifiers.numberOnly && value === "") {
        value = 0;
      }

      this.$emit("update:modelValue", Number(value));
    },
  },
};
</script>
