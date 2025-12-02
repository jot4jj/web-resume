<script setup lang="ts">
import { ref, onMounted } from "vue";
import Button from "./components/ui/button/Button.vue";
import {
  NavigationMenu,
  NavigationMenuItem,
  NavigationMenuList,
  NavigationMenuContent,
  NavigationMenuTrigger,
  NavigationMenuLink
} from "@/components/ui/navigation-menu";

import HeroSection from "./components/HeroSection.vue";
import ExperienceTimeline from "./components/ExperienceTimeline.vue";
import ProjectCard from "./components/ProjectCard.vue";
import ThemeToggle from "./components/ThemeToggle.vue";

const isDarkMode = ref(false);

onMounted(() => {
  if (localStorage.theme == "dark") {
    document.documentElement.classList.add("dark");
    isDarkMode.value = true;
  } else {
    document.documentElement.classList.remove("dark");
    isDarkMode.value = false;
  }
});

const toggleMode = () => {
  isDarkMode.value = !isDarkMode.value;
  if (isDarkMode.value) {
    document.documentElement.classList.add("dark");
    localStorage.theme = "dark";
  } else {
    document.documentElement.classList.remove("dark");
    localStorage.theme = "light";
  }
};
</script>

<template>
  <div class="min-h-screen flex flex-col items-center">
    <NavigationMenu>
      <NavigationMenuList>

        <NavigationMenuItem>
          <Button variant="ghost" class="mr-2 text-xl">Sobre Mim</Button>
        </NavigationMenuItem>

        <NavigationMenuItem>
          <Button variant="ghost" class="mr-2 text-xl">Experiencias</Button>
        </NavigationMenuItem>

        <NavigationMenuItem>
          <NavigationMenuTrigger>
            <Button variant="ghost" class="mr-2 text-xl">Projetos</Button>
          </NavigationMenuTrigger>

          <NavigationMenuContent>

            <NavigationMenuLink>
              <a href="#p1"><p>adjkksdjkasdja</p></a>
            </NavigationMenuLink>

            <NavigationMenuLink>
              <a href="#p2"><p>adjkksdjkasdja</p></a>
            </NavigationMenuLink>

            <NavigationMenuLink>
              <a href="#p3"><p>adjkksdjkasdja</p></a>
            </NavigationMenuLink>

          </NavigationMenuContent>
        </NavigationMenuItem>

        <NavigationMenuItem>
          <ThemeToggle @toggle="toggleMode" :isDarkMode="isDarkMode">Trocar tema</ThemeToggle>
        </NavigationMenuItem>

      </NavigationMenuList>
    </NavigationMenu>

    <main class="container justify-center place-items-center mx-auto px-4 py-8 space-y-16">
      <HeroSection />
      <ExperienceTimeline />
      <ProjectCard />
    </main>  

  </div>
</template>
