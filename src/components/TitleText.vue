<script setup lang="ts">
defineProps<{
  title?: string;
  sub_title?: string;
}>();
</script>

<template>
  <div class="flex justify-between items-end">
    <h3 class="head-text">
      {{ title }} <span class="text-[#42b883]">{{ sub_title }}</span>
    </h3>
    <a class="flex gap-2"
      ><p class="text-white">Show all jobs</p>
      <img src="/assets/icons/next.png" class="w-6 h-6"
    /></a>
  </div>
</template>
