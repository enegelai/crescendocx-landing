<template>
  <PageHeader></PageHeader>
  <!--<div class="absolute z-20 top-0 inset-x-0 flex justify-center overflow-hidden pointer-events-none">
    <div class="w-[108rem] flex-none flex justify-end">
      <picture>
        <img src="/media/docs@tinypng.d9e4dcdc.png" alt="" class="w-[71.75rem] flex-none max-w-none dark:hidden" decoding="async" />
      </picture>
      <picture>
        <img src="/media/docs-dark@tinypng.1bbe175e.png" alt="" class="w-[90rem] flex-none max-w-none hidden dark:block" decoding="async" />
      </picture>
    </div>
  </div>-->
  <div class="space-y-20 sm:space-y-32 md:space-y-40 lg:space-y-44 overflow-hidden bg-slate-50 dark:bg-[#0B1120]">
    <div class="relative z-10 mx-auto">
      <CHeroOneDarkR1></CHeroOneDarkR1>
      <CHeroVideo></CHeroVideo>
      <CHeroSupportedDarkR1 />
      <CHeroFeaturesLightR1></CHeroFeaturesLightR1>
      <CHeroBlogR2></CHeroBlogR2>
      <!--<CHeroOne></CHeroOne>
      <CHeroTwoDark></CHeroTwoDark>
      <CHeroTwoLight></CHeroTwoLight>
      <HeroOne></HeroOne>
      <HeroTwo></HeroTwo>
      <HeroThree></HeroThree>-->
    </div>
  </div>
  <PageFooter></PageFooter>
</template>

<script setup>
import PageHeader from './PageHeader.vue';
import HeroOne from './components/herosections/HeroOne.vue';
import CHeroOne from './components/herosections/CHeroOne.vue';
import CHeroOneDark from './components/herosections/CHeroOneDark.vue';
import CHeroOneDarkR1 from './components/herosections/CHeroOneDarkR1.vue';
import CHeroTwoLight from './components/herosections/CHeroTwoLight.vue';
import CHeroTwoDark from './components/herosections/CHeroTwoDark.vue';
import CHeroFeaturesLightR1 from './components/herosections/CHeroFeaturesLightR1.vue';
import CHeroSupportedDarkR1 from './components/herosections/CHeroSupportedDarkR1.vue';
import CHeroVideo from './components/herosections/CHeroVideo.vue';
import CHeroBlogR2 from './components/herosections/CHeroBlogR2.vue';
import HeroTwo from './components/herosections/HeroTwo.vue';
import HeroThree from './components/herosections/HeroThree.vue';
import PageFooter from './PageFooter.vue';

import { useRoute, useData } from 'vitepress';
import { computed } from 'vue';

const { theme } = useData();
const route = useRoute();

const themeConfig = computed(() => theme.value);
</script>
