import HelloWorld from './components/HelloWorld.vue';
<script setup lang="ts">
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://v3.vuejs.org/api/sfc-script-setup.html#sfc-script-setup
import BasicTabs from './components/BasicTabs.vue';
</script>

<template>
  <div class="pt-[30px] px-[12px] bg-gray-200 w-screen h-screen">
    <h2 class="text-3xl font-bold text-gray-900">BasicTabs</h2>
    <div
      class="mt-[30px] bg-green-400 px-[24px] pt-[30px] pb-[42px] rounded-md"
    >
      <div class="max-w-xl mx-auto">
        <h2 class="text-2xl font-bold text-gray-600">Basic Tabs</h2>
        <div class="mt-[24px]">
          <BasicTabs />
        </div>
      </div>
    </div>
  </div>
</template>

<style></style>
