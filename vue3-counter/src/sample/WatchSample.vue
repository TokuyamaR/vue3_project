<template>
  {{ count }}
  <button @click="increment">Increment</button>
</template>

<script>
import { ref, watch } from "vue";
export default {
  setup() {
    const count = ref(1);

    const increment = () => {
      count.value++;
    };

    // countの変更を検知し実行される
    watch(count, (next, prev) => {
      console.log(next);
      console.log(prev);
    });

    return {
      count,
      increment,
    };
  },
};
</script>
