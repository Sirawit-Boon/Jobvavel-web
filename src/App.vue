<script setup lang="ts">
import Navbar from "./sections/Navbar.vue";
import Hero from "./sections/Hero.vue";
import Category from "./sections/Category.vue";
import Jobs from "./sections/Jobs.vue";
import LatestJobs from "./sections/LatestJobs.vue";
import Footer from "./sections/Footer.vue";
</script>

<template>
  <Navbar />
  <main class="c-space max-w-7xl mx-auto">
    <Hero />
    <Category />
    <Jobs />
    <LatestJobs />
  </main>
  <Footer />
</template>
