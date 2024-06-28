<template>
  <div class="mt-20 isolate bg-c7o-strobe-light">
    <div class="mx-auto max-w-4xl">
      <p class="text-lg font-bold tracking-tight text-gray-900">Updates</p>
      <p class="mt-2 text-md leading-8 text-gray-600">
        As our business grows and evolves, the Subprocessors we utilize may also change. We will provide the owner of Customers account with notice of any new Subprocessors to the extent required under contractual
        agreement, along with posting such updates here.
        <br />
        You may also use the form below to subscribe to the updates.
      </p>
      <div id="hubspot-subprocessors-subscribe-form" class="w-1/2"></div>
    </div>
  </div>
</template>
<script setup>
import { onMounted } from 'vue';
onMounted(() => {
  console.log(`It was MOUNTED!`);
  try {
    hbspt.forms.create({
      region: 'na1',
      portalId: '44848975',
      formId: 'e21327a0-7ce3-4dad-b5d4-499e7e074e76',
      target: '#hubspot-subprocessors-subscribe-form'
    });
  } catch (e) {
    console.log(`Hubspot form failed: ${e.message}`);
  }
});
</script>
