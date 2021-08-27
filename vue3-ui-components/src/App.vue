<template>
  <ButtonSample />
  <DialogSample />
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import ButtonSample from './components/buttons/ButtonSample.vue';
import DialogSample from './components/dialog/DialogSample.vue';
export default defineComponent({
  name: 'App',
  components: {
    ButtonSample,
    DialogSample,
  },
});
</script>
