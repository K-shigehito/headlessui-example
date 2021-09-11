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
                : 'bg-green-100 text-green-500 opacity-50 hover:opacity-70',
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
            <li
              v-for="detail in details"
              :key="detail.id"
              class="bg-green-200 py-[6px] px-[12px] rounded-[3px]"
            >
              <h3 class="mb-[4px] text-[16px] text-green-600 font-bold">
                {{ detail.name }}
              </h3>
              <p class="text-[14px] text-gray-700">
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
          name: 'title A-1',
          description: 'This is dummy text.',
        },
        {
          id: 2,
          name: 'title A-2',
          description: 'This is dummy text.',
        },
      ],
      tabB: [
        {
          id: 1,
          name: 'title B-1',
          description: 'This is dummy text.',
        },
      ],
      tabC: [
        {
          id: 1,
          name: 'title C-1',
          description: 'This is dummy text.',
        },
        {
          id: 2,
          name: 'title C-2',
          description: 'This is dummy text.',
        },
        {
          id: 3,
          name: 'title C-3',
          description: 'This is dummy text.',
        },
      ],
    });

    return {
      sampleData,
    };
  },
});
</script>
