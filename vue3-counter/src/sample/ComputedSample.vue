<template>
  {{ immutable }}
  {{ mutable }}
</template>

<script>
import { ref, computed } from "vue";
export default {
  setup() {
    const count = ref(1);
    const immutable = computed(() => {
      return count.value * 2;
    });

    const mutable = computed({
      get: () => {
        return count;
      },
      set: (newValue) => {
        count.value = newValue.value;
      },
    });

    console.log((immutable.value = 3));
    console.log((mutable.value = 3));
    return {
      count,
      immutable,
      mutable,
    };
  },
};
</script>
