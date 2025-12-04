<script setup>
import { ref, onMounted } from "vue";
import {
  NavigationMenu,
  NavigationMenuItem,
  NavigationMenuList,
  NavigationMenuContent,
  NavigationMenuTrigger,
  NavigationMenuLink
} from "@/components/ui/navigation-menu";
import Button from "./ui/button/Button.vue";
import Switch from "./ui/switch/Switch.vue";

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
<NavigationMenu class="p-2 bg-[rgba(109,109,109,0.1)] border-white rounded-xl place-items-center">
    <NavigationMenuList>
        <NavigationMenuItem>
            <Button variant="ghost" class="mr-2 text-lg">Sobre Mim</Button>
        </NavigationMenuItem>

        <NavigationMenuItem>
            <Button variant="ghost" class="mr-2 text-lg">Experiencias</Button>
        </NavigationMenuItem>

        <NavigationMenuItem>
            <NavigationMenuTrigger class="bg-transparent">
                <Button variant="ghost" class="mr-2 text-lg">Projetos</Button>
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
            <Switch @toggle="toggleMode" :isDarkMode="isDarkMode"/>
        </NavigationMenuItem>
    </NavigationMenuList>
</NavigationMenu>
</template>
