import HelloWorld from './components/HelloWorld.vue';
<script setup lang="ts">
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://v3.vuejs.org/api/sfc-script-setup.html#sfc-script-setup
import BasicDisclosure from './components/BasicDisclosure.vue';
import BasicTabs from './components/BasicTabs.vue';
</script>

<template>
  <div class="pt-[24px] px-[12px] md:px-[30px] bg-gray-200 w-screen h-screen">
    <h2 class="text-[30px] font-bold text-gray-700">Headless UI samples</h2>
    <div
      class="mt-[24px] bg-green-500 px-[24px] pt-[30px] pb-[42px] rounded-md"
    >
      <div class="max-w-xl mx-auto">
        <h2 class="text-2xl font-bold text-white">Basic Tabs</h2>
        <div class="mt-[24px]">
          <BasicTabs />
        </div>
      </div>
    </div>

    <div
      class="mt-[30px] bg-indigo-500 px-[24px] pt-[30px] pb-[42px] rounded-md"
    >
      <div class="max-w-xl mx-auto">
        <h2 class="text-2xl font-bold text-white">Basic Disclosure</h2>
        <div class="mt-[24px]">
          <BasicDisclosure />
        </div>
      </div>
    </div>
  </div>
</template>

<style></style>
