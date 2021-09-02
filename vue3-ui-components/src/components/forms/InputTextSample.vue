<template name="component-name">
  <div>
    <p class="mb-2 text-2xl">Forms</p>
    <div class="w-80">
      <InputText
        v-model:value="inputTextValue"
        placeholder="placeholder"
        label="InputLabel with v-model"
      />
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue';
import InputText from './InputText.vue';

export default defineComponent({
  name: 'InputTextSample',
  components: {
    InputText,
  },
  setup() {
    const inputTextValue = ref('');

    return {
      inputTextValue,
    };
  },
});
</script>
