<template>
  <div class="isolate bg-white px-6 py-24 lg:px-8">
    <div class="mx-auto max-w-2xl text-center">
      <h2 class="text-3xl font-bold tracking-tight text-gray-900 sm:text-4xl">Say Hello</h2>
      <p class="mt-2 text-lg leading-8 text-gray-600">Please tell us about yourself</p>
    </div>
    <div id="hubspot-sayhello-form" class="mx-auto max-w-2xl text-center"></div>
  </div>
</template>

<script setup>
import { onMounted } from 'vue';
onMounted(() => {
  try {
    hbspt.forms.create({
      region: 'na1',
      portalId: '44848975',
      formId: '1d4b3d16-24fc-44f5-93ea-6a5a2f59f027',
      target: '#hubspot-sayhello-form'
    });
  } catch (e) {
    console.log(`Hubspot form failed: ${e.message}`);
  }
});
</script>
