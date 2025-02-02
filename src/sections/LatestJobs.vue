<script setup lang="ts">
import TitleText from "../components/TitleText.vue";
import ButtonTag from "../components/ButtonTag.vue";
import { latestJobs } from "../constants";
</script>
<template>
  <section class="section">
    <TitleText title="Latest" sub_title="jobs open" />
    <div class="grid grid-cols-1 lg:grid-cols-2 gap-4 mt-10">
      <div v-for="job in latestJobs" :key="job.id" class="box md:flex gap-2 md:gap-10 lg:p-10 p-4">
        <div class="min-w-[64px]">
          <img :src="job.src" alt="" class="mt-1" />
        </div>
        <div class="flex flex-col gap-2">
          <p class="jobs-head-text">{{ job.name }}</p>
          <div class="flex gap-2">
            <img src="/assets/icons/address2.png" class="w-6 h-6" />
            <p class="jobs-sub-text">{{ job.district }}, {{ job.city }}, <span>{{ job.country }}</span></p>
          </div>
          <div class="flex items-center gap-2">
            <img src="/assets/icons/thai-baht.png" class="w-6 h-6" />
            <p class="text-neutral-300">{{ job.salary_range }}</p>
          </div>
          <div class="flex gap-2 items-center mt-2">
            <ButtonTag :tag="job.type"/>
            <div class="border-l-2 border-neutral-500 h-3/4"></div>
            <ButtonTag v-for="tag in job.tag" :key="tag" :tag="tag"/>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
