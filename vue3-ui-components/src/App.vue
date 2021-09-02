<template>
  <ButtonSample />
  <DialogSample />
  <InputTextSample />
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import ButtonSample from './components/buttons/ButtonSample.vue';
import DialogSample from './components/dialog/DialogSample.vue';
import InputTextSample from './components/input/InputTextSample.vue';
export default defineComponent({
  name: 'App',
  components: {
    ButtonSample,
    DialogSample,
    InputTextSample,
  },
});
</script>
