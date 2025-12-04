<script setup lang="ts">
import HeroSection from "./components/HeroSection.vue";
import ExperienceTimeline from "./components/ExperienceTimeline.vue";
import ProjectCard from "./components/ProjectCard.vue";
import Navigation from "./components/Navigation.vue";
import Plasma from "./animations/Plasma.vue";

</script>

<template>
  <div class="w-full h-full z-0 absolute">
    <Plasma
      color="#FFFFFF"
      :speed="1"
      direction="forward"
      :scale="2"
      :opacity="0.5"
      :mouseInteractive="false"
    />
  </div>
  <div class="min-h-screen flex flex-col items-center z-50">
    <div class="my-4">
      <Navigation/>
    </div> 
    <main class="container justify-center place-items-center mx-auto px-4 py-8 space-y-16">
      <HeroSection class="z-50" />
      <ExperienceTimeline class="z-50" />
      <ProjectCard class="z-50"/>
    </main>  
  </div>
</template>
