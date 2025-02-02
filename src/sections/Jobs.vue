<script setup lang="ts">
import TitleText from "../components/TitleText.vue";
import ButtonTag from "../components/ButtonTag.vue";
import { typeStyles } from "../constants";
import { featuredJobs } from "../constants";
</script>

<template>
  <section class="section">
    <TitleText title="Featured" sub_title="jobs" />
    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-4 mt-10">
      <div
        v-for="job in featuredJobs"
        :key="job.id"
        class="box flex flex-col gap-3 p-4"
      >
        <div class="flex justify-between items-start">
          <img :src="job.src" alt="" class="w-12 h-12" />
          <div
            :class="[typeStyles[job.type]?.border || 'border-neutral-200']"
            :style="
              job.type === 'Full Time'
                ? { color: typeStyles[job.type]?.text }
                : ''
            "
            class="border p-2 rounded text-neutral-200"
          >
            {{ job.type }}
          </div>
        </div>
        <div class="">
          <p class="text-[18px] font-semibold text-white">{{ job.name }}</p>
          <p class="text-neutral-300 mt-3">
            {{ job.district }}, {{ job.city }} City
          </p>
          <p class="text-neutral-300">{{ job.country }}</p>
        </div>
        <div class="flex items-center gap-2">
          <img src="/assets/icons/thai-baht.png" class="w-6 h-6" />
          <p class="text-neutral-300">{{ job.salary_range }}</p>
        </div>
        <div class="flex gap-2">
          <ButtonTag v-for="tag in job.tag" :key="tag" :tag="tag" />
        </div>
      </div>
    </div>
  </section>
</template>
