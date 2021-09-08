<template>
  <div class="w-full">
    <TabGroup>
      <TabList class="flex space-x-[4px]">
        <Tab
          v-for="category in Object.keys(sampleData)"
          :key="category"
          v-slot="{ selected }"
        >
          <button
            :class="[
              selected
                ? 'bg-green-100 text-green-700'
                : 'bg-green-100 text-green-500 opacity-50',
            ]"
            class="py-[6px] px-[24px] rounded-t-[4px] font-bold"
          >
            {{ category }}
          </button>
        </Tab>
      </TabList>

      <TabPanels>
        <TabPanel
          v-for="(details, index) in Object.values(sampleData)"
          :key="index"
          :class="[
            'px-[18px] py-[24px] bg-green-100 rounded-b-[4px] rounded-tr-[4px] shadow-md',
          ]"
        >
          <ul class="flex flex-col gap-[24px]">
            <li v-for="detail in details" :key="detail.id">
              <h3 class="mb-[4px] text-[16px] text-green-600 font-bold">
                {{ detail.name }}
              </h3>
              <p class="text-[12px] text-gray-700">
                {{ detail.description }}
              </p>
            </li>
          </ul>
        </TabPanel>
      </TabPanels>
    </TabGroup>
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue';
import { TabGroup, TabList, Tab, TabPanels, TabPanel } from '@headlessui/vue';

export default defineComponent({
  name: 'BasicTabs',
  components: {
    TabGroup,
    TabList,
    Tab,
    TabPanels,
    TabPanel,
  },

  setup() {
    const sampleData = ref({
      tabA: [
        {
          id: 1,
          name: 'タイトルA-1',
          description:
            'ダミーテキストです。ダミーテキストです。ダミーテキストです。',
        },
        {
          id: 2,
          name: 'タイトルA-2',
          description:
            'ダミーテキストです。ダミーテキストです。ダミーテキストです。ダミーテキストです。ダミーテキストです。ダミーテキストです。ダミーテキストです。',
        },
      ],
      tabB: [
        {
          id: 1,
          name: 'タイトルB-1',
          description:
            'ダミーテキストです。ダミーテキストです。ダミーテキストです。',
        },
        {
          id: 2,
          name: 'タイトルB-2',
          description:
            'ダミーテキストです。ダミーテキストです。ダミーテキストです。',
        },
      ],
      tabC: [
        {
          id: 1,
          name: 'タイトルC-1',
          description:
            'ダミーテキストです。ダミーテキストです。ダミーテキストです。ダミーテキストです。ダミーテキストです。ダミーテキストです。ダミーテキストです。',
        },
        {
          id: 2,
          name: 'タイトルC-2',
          description:
            'ダミーテキストです。ダミーテキストです。ダミーテキストです。ダミーテキストです。ダミーテキストです。ダミーテキストです。ダミーテキストです。',
        },
      ],
    });

    return {
      sampleData,
    };
  },
});
</script>
