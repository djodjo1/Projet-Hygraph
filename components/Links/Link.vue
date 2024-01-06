<script setup>
defineProps({
  to: {
    type: String,
    required: true,
  },
});
</script>

<template>
  <NuxtLink
    :to="to"
    class="text-gray-300 hover:text-gray-100 underline transition"
  >
    <slot />
  </NuxtLink>
</template>
