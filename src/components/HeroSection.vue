<script setup>
import Button from "./ui/button/Button.vue";
import { Avatar, AvatarFallback, AvatarImage } from "@/components/ui/avatar";
import { Github, Linkedin } from "lucide-vue-next";
</script>

<template>
    <section>
        <Avatar class="w-48 h-48 md:w-64 md:h-64">
            <AvatarImage src="https://avatars.githubusercontent.com/u/153793737?v=4"/>
        </Avatar>
        <div class="space-y-4">
            <h2 class="text-4xl font-extrabold tracking-tight lg:text-5xl">
                Olá, me chamo <span class="text-primary">Joao Vitor</span>
            </h2>
            <p class="text-xl text-muted-foreground">
                Desenvolvedor Web Full Stack com paixão por Vue.js, interfaces de usuário incríveis e código limpo. Construindo experiências digitais que importam.
            </p>
            <div class="flex justify-center md:justify-start gap-4 mt-6">
                <a href="https://github.com/jot4jj" target="_blank">
                    <Github />
                </a>
                <a href="">
                    <Linkedin />
                </a>
            </div>
        </div>
    </section>
</template>
