<script setup lang="ts">

import HeroSection from "@/components/section/HeroSection.vue";
import VerticalStepper from "@/components/ScrollProgress.vue";
import CareerSection from "@/components/section/CareerSection.vue";
import ProjectSection from "@/components/section/ProjectSection.vue";
</script>

<template>
  <div class="flex flex-row">
    <div class="flex-[20%]">
      <VerticalStepper />
    </div>
    <div class="flex-[80%]">
      <HeroSection />
      <CareerSection />
      <ProjectSection />
    </div>
  </div>
</template>

<style scoped>

</style>
