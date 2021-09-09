<template>
  <!-- オープンボタン -->
  <div class="">
    <button
      type="button"
      class="
        px-[18px]
        py-[12px]
        text-sm
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

  <Dialog
    :open="isOpen"
    class="fixed inset-0 z-10 overflow-y-auto"
    @close="setIsOpen"
  >
    <div class="flex items-center justify-center min-h-screen">
      <DialogOverlay class="fixed inset-0 bg-gray-800 opacity-30" />

      <div class="relative max-w-sm mx-auto bg-white rounded-[6px]">
        <DialogTitle>Deactivate account</DialogTitle>
        <DialogDescription>
          This will permanently deactivate your account
        </DialogDescription>

        <p>
          Are you sure you want to deactivate your account? All of your data
          will be permanently removed. This action cannot be undone.
        </p>

        <button @click="setIsOpen(false)">Deactivate</button>
        <button @click="setIsOpen(false)">Cancel</button>
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
