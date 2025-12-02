<script setup>
import Button from "./ui/button/Button.vue";
import { Avatar, AvatarFallback, AvatarImage } from "@/components/ui/avatar";
import { Github, Linkedin } from "lucide-vue-next";
import SplitText from "@/animations/SplitText.vue";

</script>

<template>
    <section class="min-h-screen w-2/3 flex place-items-center gap-10">

        <Avatar class=" md:w-100 md:h-100">
            <AvatarImage src="https://avatars.githubusercontent.com/u/153793737?v=4"/>
        </Avatar>

        <div class="space-y-6">

            <p>Desenvolvedor Front-end</p>

            <h2 class="text-5xl font-extrabold tracking-tight lg:text-5xl">
                <SplitText
                    text="Olá, eu me chamo João Vitor"
                    class-name="text-5xl font-extrabold"
                    :delay="80"
                    :duration="0.2"
                    ease="power3.out"
                    split-type="chars"
                    :from="{ opacity: 0, y: 40 }"
                    :to="{ opacity: 1, y: 0 }"
                    :threshold="0.1"
                    root-margin="-100px"
                    text-align="center"
                    @animation-complete="handleAnimationComplete"
                />
            </h2>

            <p class="text-2xl text-muted-foreground">
                Lorem ipsum dolor sit amet consectetur adipisicing elit. Voluptatem fugiat illum tempora enim aperiam sapiente ducimus? Officiis similique, architecto dolorem nihil ipsum numquam cum exercitationem sint mollitia? Aliquam, alias minima.
            </p>

            <div class="flex w-full justify-around">
                <div>
                    <a href="https://github.com/jot4jj" target="_blank"> <Github /> </a>
                </div>
                
                <div>
                    <a href="https://www.linkedin.com/in/jo%C3%A3o-vitor-silva-freitas-b8a13538b/" target="_blank"> <Linkedin /></a>
                </div>
            </div>

        </div>
    </section>
</template>
