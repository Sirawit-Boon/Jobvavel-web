<script setup lang="ts">
import { aboutLinks, resourceLinks, socailLinks } from "../constants";
</script>
<template>
  <section
    class="flex w-full lg:mt-20 mt-12 gap-10 bg-[#1A1D21] border-t border-[#363A3D] justify-center py-10"
  >
    <div class="c-space mx-auto flex flex-col max-w-7xl w-full gap-10">
      <div class="md:flex justify-between w-full">
        <div class="flex flex-col gap-5 max-w-[375px]">
          <div class="flex gap-4 items-center">
            <a>
              <img src="/assets/icons/logo.png" class="w-12 h-12" />
            </a>
            <h1 class="font-semibold text-2xl text-[#42b883]">
              JobVavel
            </h1>
          </div>
          <p class="jobs-sub-text">
            Great platform for the job seeker that passionate about startups.
            Find your dream job easier.
          </p>
        </div>
        <div class="footer-section">
          <h3 class="font-semibold text-xl text-[#42b883]">About</h3>
          <ul class="flex flex-col gap-2">
            <li
              v-for="about in aboutLinks"
              :key="about.id"
              class="jobs-sub-text"
            >
              <a :href="about.href" class="">{{ about.name }}</a>
            </li>
          </ul>
        </div>
        <div class="footer-section">
          <h3 class="font-semibold text-xl text-[#42b883]">Resources</h3>
          <ul class="flex flex-col gap-2">
            <li
              v-for="resource in resourceLinks"
              :key="resource.id"
              class="jobs-sub-text"
            >
              <a :href="resource.href" class="">{{ resource.name }}</a>
            </li>
          </ul>
        </div>
        <div class="footer-section">
          <h3 class="font-semibold text-xl text-[#42b883]">
            Get job notifications
          </h3>
          <p class="jobs-sub-text">
            The latest job news, articles, sent to your inbox weekly.
          </p>
          <div class="flex gap-2">
            <input
              type="text"
              class="bg-white p-2 rounded"
              placeholder="Email Address"
            />
            <button class="btn">Subscribe</button>
          </div>
        </div>
      </div>
      <div class="border-t border-[#363A3D]">
        <div class="md:flex-row justify-between items-center lg:gap-12 mt-7 flex flex-col gap-5">
          <p class="jobs-sub-text">2025 @ JobVavel. All rights reserved.</p>
          <div class="flex gap-5">
            <div
              v-for="social in socailLinks"
              :key="social.id"
              class="rounded-md bg-gradient-to-r from-[#42b883] to-[#2e8c6a] w-8 h-8"
            >
              <a
                :href="social.href"
                class="flex justify-center items-center h-full"
                ><img :src="social.src" alt="" class="w-8 h-8"
              /></a>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
