<template>
  <div class="h-screen">
    <Samples />
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import Samples from './views/Samples.vue';
export default defineComponent({
  components: { Samples },
});
</script>
