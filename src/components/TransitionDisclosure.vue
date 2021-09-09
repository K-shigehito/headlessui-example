<template>
  <div class="w-full">
    <div
      class="p-2 bg-pink-100 rounded-[4px] flex flex-col gap-[12px] shadow-md"
    >
      <Disclosure v-for="data in sampleData" v-slot="{ open }" :key="data.id">
        <div>
          <DisclosureButton
            class="
              flex
              justify-between
              w-full
              px-[24px]
              py-[12px]
              text-[14px]
              font-bold
              text-pink-800
              bg-pink-300
              rounded-[6px]
              hover:opacity-80
            "
          >
            <span> {{ data.question }}</span>
            <ChevronRightIcon
              :class="open ? 'transform rotate-90' : ''"
              class="w-5 h-5 text-pink-500"
            />
          </DisclosureButton>

          <transition
            enter-active-class="transition duration-100 ease-out"
            enter-from-class="transform -translate-y-3 opacity-0"
            enter-to-class="transform translate-y-0 opacity-100"
            leave-active-class="transition duration-100 ease-out"
            leave-from-class="transform translate-y-0 opacity-100"
            leave-to-class="transform -translate-y-3 opacity-0"
          >
            <DisclosurePanel
              class="px-[24px] pt-[12px] pb-[6px] text-[14px] text-gray-700"
            >
              {{ data.answer }}
            </DisclosurePanel>
          </transition>
        </div>
      </Disclosure>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue';
import { Disclosure, DisclosureButton, DisclosurePanel } from '@headlessui/vue';
import { ChevronRightIcon } from '@heroicons/vue/solid';

export default defineComponent({
  components: {
    Disclosure,
    DisclosureButton,
    DisclosurePanel,
    ChevronRightIcon,
  },

  setup() {
    const sampleData = ref([
      {
        id: 1,
        question: 'Q1：question-1',
        answer: 'A1：answer-1',
      },
      {
        id: 2,
        question: 'Q2：question-1',
        answer: 'A2：answer-1',
      },
    ]);

    return {
      sampleData,
    };
  },
});
</script>
