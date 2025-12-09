<script setup lang="ts">
import HeroSection from "./components/HeroSection.vue";
import ExperienceTimeline from "./components/ExperienceTimeline.vue";
import ProjectCard from "./components/ProjectCard.vue";
import Navigation from "./components/Navigation.vue";
import StackBar from "./components/StackBar.vue";
import AnimatedContent from "./animations/AnimatedContent.vue";
import LightRays from "./animations/LightRays.vue";
</script>

<template>
  <AnimatedContent
    :distance="160"
    direction="vertical"
    :reverse="true"
    :duration="1"
    ease="power3.out"
    :initial-opacity="0"
    :animate-opacity="true"
    :scale="1"
    :threshold="0.1"
    :delay="0"
  >
    <div class="w-full h-full z-0 absolute">
    <LightRays
      rays-origin="top-center"
      rays-color="#5c10db"
      :rays-speed="1.5"
      :light-spread="2"
      :ray-length="1.2"
      :follow-mouse="true"
      :mouse-influence="0.1"
      :noise-amount="0.1"
      :distortion="0.05"
    />
    </div>
    <div class="min-h-screen flex flex-col items-center z-50">
      <div class="my-4">
        <Navigation />
      </div>
      <main
        class="container justify-center place-items-center mx-auto px-4 py-8 space-y-16 w-3/4"
      >
        <HeroSection id="hero" />
        <ExperienceTimeline id="experience" />
        <StackBar id="stack" />
        <ProjectCard id="projects" />
      </main>
    </div>
  </AnimatedContent>
</template>
