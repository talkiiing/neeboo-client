<template>
  <div class="flex flex-col justify-between items-center h-full w-full">
    <div class="flex flex-col justify-start items-start w-full">
      <h1 class="font-montserrat font-bold font-size text-5 leading-7 mb-6">90000 ₽</h1>
      <h2 class="m4 mb-12">название ассета</h2>
      <p class="w-72 h-72 mb-12">изображение ассета</p>
      <div class="flex flex-row justify-start items-center flex-wrap">
        <h2 class="m4 mr-5">Токен:</h2>
        <p class="r2 mr-8">wefji3ergfregregopfjufj</p>
        <ClipboardIcon class="w-5 h-5" @click="copyToken"/>
      </div>
    </div>
    <VButton class="self-center justify-self-end mb-28" @click="sellToken">Продать</VButton>
  </div>
</template>

<script>
import { ClipboardIcon } from '@heroicons/vue/outline';

import VButton from '@/components/VButton.vue';
import { useRouter } from 'vue-router';

export default {
  name: 'Token',
  components: {
    ClipboardIcon,
    VButton,
  },
  setup() {
    const router = useRouter();

    console.log(router);
    const tokenId = router.currentRoute.value.params.id;

    const copyToken = () => console.warn('TODO: copy to clipboard');
    const sellToken = () => {
      router.push(`/wallet/sellToken/${tokenId}`);
    };

    return {
      copyToken,
      sellToken,
    };
  },
};
</script>
