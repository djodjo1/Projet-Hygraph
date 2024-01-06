<script setup lang="ts">
import { ref } from "vue";

const props = defineProps({
  src: {
    type: String,
    required: true,
  },
  alt: {
    type: String,
    required: true,
  },
});

const loaded = ref(false);
</script>

<template>
  <div class="w-full aspect-square">
    <div
      v-show="!loaded"
      class="h-full w-full bg-white/50 animate-pulse flex justify-center items-center"
    >
      <i class="ri-image-line text-[5rem] text-gray-400"></i>
    </div>
    <Transition>
      <NuxtImg
        v-show="loaded"
        :src="src"
        :alt="alt"
        class="aspect-square w-full object-cover object-top !py-0 !my-0"
        @load="loaded = true"
      />
    </Transition>
  </div>
</template>

<style scoped>
.v-enter-active,
.v-leave-active {
  transition: opacity 0.6s ease;
}

.v-enter-from,
.v-leave-to {
  opacity: 0;
}
</style>
