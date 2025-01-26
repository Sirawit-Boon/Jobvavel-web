<script setup lang="ts">
import { Swiper, SwiperSlide } from "swiper/vue";
import "../../node_modules/swiper/swiper.min.css";
import "../../node_modules/swiper/modules/navigation.min.css";
import "../../node_modules/swiper/modules/pagination.min.css";
import "../../node_modules/swiper/modules/autoplay.min.css";
import { Navigation, Pagination, EffectCoverflow, Autoplay } from "swiper/modules";
import { companiesAds } from "../constants";
import Companies from "../components/Companies.vue";
</script>

<template>
  <section
    class="w-full flex flex-col md:flex-row lg:mt-20 mt-12 gap-5 justify-between"
  >
    <div class="md:w-1/2 flex flex-col gap-5 text-center md:text-start">
      <h1 class="hero-head_text text-white hidden md:flex">
        Discover <br />morethan
      </h1>
      <h1 class="hero-head_text text-white md:hidden">Discover morethan</h1>
      <p class="text-[#26A4FF] hero-head_text">5000+ Jobs</p>
      <p class="sub-text">
        Great platform for the job seeker that searching for new career heights
        and passionate about startups.
      </p>
      <div class="w-full">
        <form
          class="flex flex-col lg:flex-row w-full gap-2 justify-between bg-[#1A1D21] border border-[#363A3D] p-4 items-center"
        >
          <label class="flex items-start gap-3 w-full">
            <img src="/assets/search.svg" class="h-6 w-6" />
            <input class="input w-full" placeholder="Job title or Keyword" />
          </label>
          <label class="flex items-start gap-3 w-full">
            <img src="/assets/address.png" class="h-6 w-6" />
            <select class="input w-full">
              <option value="address">Select your address</option>
            </select>
          </label>
          <button
            class="bg-[#42b883] p-2 text-white font-semibold rounded mt-4 md:mt-0"
          >
            Search
          </button>
        </form>
        <p class="text-neutral-200 mt-4">
          Popular : Programmer, Developer, Android, Admin
        </p>
      </div>
    </div>
    <div class="md:w-1/2 overflow-hidden">
      <Swiper
        class="lg:h-[440px] h-[300px] w-full"
        :modules="[Navigation, Pagination, EffectCoverflow, Autoplay]"
        effect="coverflow"
        :grabCursor="true"
        :centeredSlides="true"
        :initialSlide="1"
        :speed="600"
        :preventClicks="true"
        :slidesPerView="2"
        :coverflowEffect="{
          rotate: 0,
          stretch: 80,
          depth: 250,
          modifier: 1,
          slideShadows: true,
        }"
        pagination
        :autoplay="{ delay: 3000, disableOnInteraction: false }"
      >
        <SwiperSlide v-for="company in companiesAds" :key="company.id"
          ><img :src="company.src" :alt="company.name" />
          <div class="company-name">
            <span>{{ company.name }}</span>
          </div></SwiperSlide
        >
      </Swiper>
    </div>
  </section>
  <Companies />
</template>
