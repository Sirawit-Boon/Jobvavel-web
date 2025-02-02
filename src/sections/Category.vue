<script setup lang="ts">
import { jobCategories } from "../constants";
import TitleText from "../components/TitleText.vue";
</script>
<template>
  <section class="w-full flex flex-col">
    <TitleText title="Explore By" sub_title="Category"/>
    <div class="grid grid-cols-1 md:grid-cols-3 lg:grid-cols-4 gap-4 mt-10">
      <div
        v-for="category in jobCategories"
        :key="category.id"
        class="box"
      >
        <div class="relative">
          <img :src="category.src" :alt="category.name" />
          <p
            class="text-white font-semibold text-xl absolute bg-gradient-to-r from-[#42b883] to-[#2e8c6a] shadow-lg bottom-4 px-2 py-1 rounded-md rounded-l-none"
          >
            {{ category.name }}
          </p>
        </div>
        <div class="flex flex-col gap-2 px-4 py-3">
          <div class="flex items-center gap-2">
            <img src="/assets/icons/thai-baht.png" class="w-6 h-6" />
            <p class="text-neutral-300">
              {{ category.min_salary }} - {{ category.max_salary }}
            </p>
          </div>
          <a class="text-neutral-300 flex gap-2 just">
            <img src="/assets/icons/job2.png" class="w-6 h-6" />
            <p>{{ category.available }} jobs available</p>
          </a>
        </div>
      </div>
    </div>
    <div
      class="flex flex-col md:flex-row md:mt-20 mt-12 bg-[#1A1D21] rounded-md justify-between"
    >
      <div class="md:p-10 p-5 flex flex-col gap-6 items-start justify-start">
        <h3 class="text-5xl text-white font-semibold hidden md:block">
          Start posting jobs <br /><span class="">today</span>
        </h3>
        <h3 class="text-5xl text-white font-semibold md:hidden">
          Start posting jobs <span class=""> today</span>
        </h3>
        <p class="text-white">
          Start posting jobs to find the right employees for your company.
        </p>
        <button class="btn">Sign Up For Free</button>
      </div>
      <!-- <div class="">
        <img src="/assets/dashboard.png" class="shadow-2xl rounded-lg" />
      </div> -->
    </div>
  </section>
</template>
