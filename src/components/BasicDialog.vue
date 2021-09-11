<template>
  <!-- オープンボタン -->
  <div class="">
    <button
      type="button"
      class="
        px-[18px]
        py-[8px]
        font-bold
        text-[16px] text-yellow-800
        bg-yellow-100
        shadow-sm
        rounded-[6px]
        hover:bg-opacity-70
      "
      @click="setIsOpen(true)"
    >
      Open
    </button>
  </div>

  <!-- ダイアログ -->
  <Dialog
    :open="isOpen"
    class="fixed inset-0 z-10 overflow-y-auto"
    @close="setIsOpen"
  >
    <div class="flex items-center justify-center min-h-screen">
      <DialogOverlay class="fixed inset-0 bg-gray-800 opacity-60" />

      <div
        class="
          relative
          max-w-md
          mx-auto
          px-[24px]
          py-[12px]
          bg-yellow-50
          rounded-[6px]
        "
      >
        <DialogTitle>
          <h2 class="text-[24px] text-yellow-800 font-bold">Title</h2>
        </DialogTitle>
        <DialogDescription>
          <p class="mt-[2px] text-[18px] text-gray-700 font-bold">
            Description
          </p>
        </DialogDescription>

        <p class="mt-[12px] text-gray-700">
          This is simple modal component sample. This is simple modal component
          sample.
        </p>

        <div class="flex gap-[8px] justify-end mt-[18px] ml-auto">
          <button
            class="
              px-[12px]
              py-[6px]
              text-[16px] text-yellow-100
              bg-yellow-500
              shadow-sm
              rounded-[6px]
              hover:bg-opacity-70
            "
            @click="setIsOpen(false)"
          >
            OK
          </button>
          <button
            class="
              px-[12px]
              py-[6px]
              text-[16px] text-gray-100
              bg-gray-500
              shadow-sm
              rounded-[6px]
              hover:bg-opacity-70
            "
            @click="setIsOpen(false)"
          >
            Cancel
          </button>
        </div>
      </div>
    </div>
  </Dialog>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue';
import {
  Dialog,
  DialogOverlay,
  DialogTitle,
  DialogDescription,
} from '@headlessui/vue';

export default defineComponent({
  components: { Dialog, DialogOverlay, DialogTitle, DialogDescription },
  setup() {
    const isOpen = ref(false);
    const setIsOpen = (value: boolean) => {
      isOpen.value = value;
    };

    return {
      isOpen,
      setIsOpen,
    };
  },
});
</script>
