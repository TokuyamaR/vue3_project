<template>
  <div>
    <p class="mb-2 text-2xl">Dialog</p>
    <div>
      <MyDialog :visible="dialogVisible" @backdrop-clicked="switchDialog">
        <template #title>
          <p class="font-bold">ダイアログ</p>
        </template>
        <template #body>
          2012年3月10日、北海道沙流郡日高町・ヤナガワ牧場にて誕生。父は2004年のスプリングステークス優勝馬で、全弟に2005年のクラシック三冠を含むGI7勝を挙げたディープインパクトを持つブラックタイド[9]。母のシュガーハートはヤナガワ牧場の生産馬で、生まれたときから牧場でも高く評価されていたが、デビュー前に屈腱炎を発症して未出走のまま繁殖入りしていた[10]。同牧場の代表を務める梁川正普（やながわ・まさひろ）は、幼少期のキタサンブラックについて「（キタサンブラックは）体つきがよくて、走りも素軽かったですね。いい馬だと思いました。ただ、1歳くらいになると、脚がグンッと伸びたので、そこだけは心配でした。あまりに脚が伸びて体高が高くなると、バランスが悪くなってしまうので。それで、しばらくは不安もあったのですが、結局は大した問題にもならず、（牧場の）期待馬になっていました。もちろん、GIを勝てるとまでは思いませんでしたけど（笑）」と述べている
        </template>
        <template #footer>
          <div class="flex justify-end">
            <SecondaryButton @click="switchDialog">close</SecondaryButton>
          </div>
        </template>
      </MyDialog>
    </div>
    <div class="mb-2">
      <PrimaryButton @click="switchDialog">close</PrimaryButton>
    </div>
  </div>
</template>
<script lang="ts">
import { defineComponent, ref } from 'vue';
import PrimaryButton from '../buttons/PrimaryButton.vue';
import SecondaryButton from '../buttons/SecondaryButton.vue';
import MyDialog from './MyDialog.vue';

export default defineComponent({
  name: 'DialogSample',
  components: {
    PrimaryButton,
    SecondaryButton,
    MyDialog,
  },
  setup() {
    const dialogVisible = ref(false);
    const switchDialog = () => {
      dialogVisible.value = !dialogVisible.value;
    };

    return {
      dialogVisible,
      switchDialog,
    };
  },
});
</script>
