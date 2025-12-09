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
import { Menu } from "lucide-vue-next";

const isDarkMode = ref(false);
const isOpen = ref(false);

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

const toggleMenu = () => {
    isOpen.value = !isOpen.value
}

</script>

<template>
<NavigationMenu class="p-2 bg-[rgba(109,109,109,0.1)] border-white rounded-xl place-items-center left-1/2 right-1/2 w-full -translate-1/2 my-6 z-50 hidden md:fixed sm:flex backdrop-blur-md scroll-smooth">
    <NavigationMenuList>
        <NavigationMenuItem>
            <a href="#project"><Button variant="ghost" class="mr-2 text-lg">Sobre Mim</Button></a>
        </NavigationMenuItem> 

        <NavigationMenuItem>
            <a href="#experience"><Button variant="ghost" class="mr-2 text-lg">Experiencias</Button></a>
        </NavigationMenuItem>
        
        <NavigationMenuItem>
            <a href="#stack"><Button variant="ghost" class="mr-2 text-lg">Tecnologias</Button></a>
        </NavigationMenuItem>

        <NavigationMenuItem>
            <NavigationMenuTrigger class="bg-transparent">
                <a href="#projects"><Button variant="ghost" class="mr-2 text-lg">Projetos</Button></a>
            </NavigationMenuTrigger>

            <NavigationMenuContent>
                <NavigationMenuLink>
                    <a href=""><p>adjkksdjkasdja</p></a>
                </NavigationMenuLink>

                <NavigationMenuLink>
                    <a href=""><p>adjkksdjkasdja</p></a>
                </NavigationMenuLink>
            </NavigationMenuContent>
        </NavigationMenuItem>

        <NavigationMenuItem>
            <Switch @toggle="toggleMode" :isDarkMode="isDarkMode"/>
        </NavigationMenuItem>
    </NavigationMenuList>
</NavigationMenu>


<Button
    class="sm:hidden fixed top-5 left-5 z-50 p-2 rounded-lg bg-[rgba(109,109,109,0.1)] backdrop-blur-md"
    @click="toggleMenu"
>
    <Menu color="white"/>
</Button>

<div
    v-if="isOpen"
    class="md:hidden fixed top-0 left-0 w-3/4 h-full bg-white dark:bg-[rgba(0,0,0,0.8)] backdrop-blur-md shadow-xl z-40 p-6 flex flex-col transition-all"
>
    <div class="my-10">
        <div>
            <a href="#project" @click="toggleMenu"><p class="text-lg">Sobre Mim</p></a>
        </div>

        <div>
            <a href="#experience" @click="toggleMenu"><p class="text-lg">Experiências</p></a>
        </div>
    
        <div>
            <a href="#stack" @click="toggleMenu"><p class="text-lg">Tecnologias</p></a>
        </div>

        <div>
        <details>
            <summary class="text-lg">Projetos</summary>
            <ul class="pl-4 mt-2 flex flex-col gap-2">
                <li><a href="">adjkksdjkasdja</a></li>
                <li><a href="">adjkksdjkasdja</a></li>
            </ul>
        </details>
        </div>

        <div>
            <Switch @toggle="toggleMode" :isDarkMode="isDarkMode" />
        </div>
    </div>
    
</div>
</template>
