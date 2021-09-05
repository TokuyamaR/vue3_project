<template>
  <div>
    <p class="text-2xl mb">ContentsLoader</p>
    <ContentsLoader :line="2" />
  </div>
  <div>
    <p>fetch data</p>
    <Suspense>
      <!-- 非同期処理後に表示 -->
      <template #default>
        <PostView />
      </template>
      <!-- 非同期処理が完了されるまでの代替コンテンツが表示される  -->
      <template #fallback>
        <ContentsLoader :line="3" />
      </template>
    </Suspense>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import PostView from '../PostView.vue';
import ContentsLoader from './ContentsLoader.vue';
export default defineComponent({
  name: 'ContentsLoaderSample',
  components: {
    ContentsLoader,
    PostView,
  },
});
</script>
