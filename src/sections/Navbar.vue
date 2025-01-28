<script setup lang="ts">
import { ref } from "vue";
import { navLinks } from "../constants";

const isOpen = ref<boolean>(false);
</script>

<template>
  <header>
    <div
      class="c-space w-full mx-auto flex justify-between bg-[#0D0F10] #0D0F10 #42b883 items-center"
    >
      <div class="flex justify-between gap-12">
        <div class="flex flex-col sm:flex-row items-center gap-4">
          <a>
            <img src="/assets/icons/logo.png" class="md:w-20 md:h-20 w-14 h-14" />
          </a>
          <h1 class="font-semibold text-xl text-[#42b883] hidden md:flex">
            JobVavel
          </h1>
        </div>
        <nav class="nav-ul text-white #35495e">
          <a> Jobs </a>
          <a> Companies </a>
        </nav>
      </div>
      <div class="nav-ul">
        <button class="btn">Login</button>
        <button class="btn">Sing up</button>
      </div>
      <div class="sm:hidden flex">
        <button
          class="text-neutral-400 hover:text-white focus:outline-none"
          @click="isOpen = !isOpen"
        >
          <img
            :src="isOpen ? '/assets/icons/close.svg' : '/assets/icons/menu.svg'"
            class="w-6 h-6"
          />
        </button>
      </div>
    </div>
    <div :class="['nav-sidebar', isOpen ? 'max-h-screen' : 'max-h-0']">
      <nav class="p-5">
        <ul class="nav-ul_mobile">
          <li v-for="link in navLinks" :key="link.id" class="nav-li">
            <a :href="link.href" class="nav-li_a">{{ link.name }}</a>
          </li>
        </ul>
      </nav>
    </div>
  </header>
</template>
