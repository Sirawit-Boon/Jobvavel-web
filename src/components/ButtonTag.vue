<script setup lang="ts">
import { tagStyles } from "../constants";
defineProps<{
  tag?: string;
}>();
</script>

<template>
  <button
    :class="[tag ? tagStyles[tag]?.bg : 'bg-gray-200/10']"
    :style="{ color: tag ? tagStyles[tag]?.text : '#000' }"
    class="rounded-2xl p-2"
  >
    {{ tag }}
  </button>
</template>
