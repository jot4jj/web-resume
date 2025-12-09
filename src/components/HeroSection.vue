<script setup>
import Button from "./ui/button/Button.vue";
import { Avatar, AvatarFallback, AvatarImage } from "@/components/ui/avatar";
import SplitText from "@/animations/SplitText.vue";
import ProfileCard from "@/animations/ProfileCard.vue";
import { Globe, Github, Linkedin } from "lucide-vue-next";
</script>

<template>
    <section class="min-h-screen w-full flex flex-col place-items-center z-50 xl:flex-row lg:w-3/5">
        <div class="space-y-6 gap-10 flex flex-col place-items-center lg:flex-row">
            <div class="my-10 lg:my-0">
                <ProfileCard
                    name="João Vitor S."
                    title="Desenvolvedor Front-end"
                    avatar-url="./img/profile.png"
                    :show-user-info="false"
                    :show-behind-gradient="true"
                    :enable-tilt="true"
                />
            </div>

            <div class="flex flex-col gap-10 h-full justify-between">
                <div>
                    <p class="text-xl md:text-2xl text-justify relative h-full">
                        Sou João Vitor, desenvolvedor Front-end apaixonado por transformar ideias em interfaces modernas, funcionais e bem estruturadas. Desde 2022 estudo programação e, ao longo da minha formação em Desenvolvimento de Sistemas, venho me especializando em desenvolvimento web, criando projetos que unem boa estética, desempenho e experiência do usuário.
                    </p>
                </div>

                <div class="flex w-full justify-between relative gap-10">

                    <div class="w-full">
                        <a href="https://github.com/jot4jj" target="_blank" >
                            <Button class="cursor-target w-full"> <Github /></Button>
                        </a>
                    </div>
                    
                    <div class="w-full">
                        <a href="https://www.linkedin.com/in/jo%C3%A3o-vitor-silva-freitas-b8a13538b/" target="_blank">
                            <Button class="cursor-target w-full"> <Linkedin /></Button>
                        </a>
                    </div>

                </div>

            </div>

        </div>
    </section>
</template>
