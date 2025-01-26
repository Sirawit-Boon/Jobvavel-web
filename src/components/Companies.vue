<script setup lang="ts">
import { companiesLogo } from "../constants";
</script>
<template>
  <section class="w-full md:mt-20 mt-12 h-52 gap-4">
    <h2 class="sub-text">Top Companies People Aspire to Work For</h2>
    <div class="md:flex grid grid-cols-3 md:flex-row justify-between mt-5 items-center">
      <img
        v-for="company in companiesLogo"
        :key="company.id"
        :class="company.width"
        :src="company.src"
        :alt="company.name"
      />
    </div>
  </section>
</template>
