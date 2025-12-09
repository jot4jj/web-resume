<script setup>
import {
    Card,
    CardAction,
    CardDescription,
    CardHeader,
    CardTitle,
    CardContent,
    CardFooter
} from './ui/card';
import GradientText from '@/animations/GradientText.vue';
import SpotlightCard from '@/animations/SpotlightCard.vue';
import Button from './ui/button/Button.vue';
import { Globe, Github } from 'lucide-vue-next';

const projects = [
    {
        title: 'Pokédex com Vue.js e TailwindCSS',
        description: 'Uma Pokédex interativa desenvolvida com Vue 3, TailwindCSS, Axios e a PokéAPI, permitindo buscar Pokémon por nome, tipo ou geração. O projeto foi criado com foco em boas práticas de componentização (Atomic Design) e uma UI responsiva e limpa',
        preview: '/img/preview-pokedex.png',
        githubUrl: 'https://github.com/jot4jj/pokedex-vue-tailwind',
        webUrl: 'https://pokedex-vue-tailwind.vercel.app/#/',
        stack: [
            {
                name: 'Vue.js',
                iconUrl: 'https://skillicons.dev/icons?i=vue'
            },
            {
                name: 'Java Script',
                iconUrl: 'https://skillicons.dev/icons?i=js'
            },
            {
                name: 'TailwindCSS',
                iconUrl: 'https://skillicons.dev/icons?i=tailwindcss'
            },
                        {
                name: 'Figma',
                iconUrl: 'https://skillicons.dev/icons?i=figma'
            }
        ]
    },
    {
        title: 'Mapa interativo com Leaflet.js',
        description: 'Um mapa interativo desenvolvido com Vue 3, Leaflet e TailwindCSS, permitindo visualizar pontos, áreas e informações geográficas em tempo real. O projeto destaca boas práticas de componentização, UI responsiva e integração fluida com dados geoespaciais.',
        preview: '/img/preview-map.png',
        githubUrl: 'https://github.com/jot4jj/interactive-map-leaflet',
        webUrl: 'https://interactive-map-leaflet.vercel.app/',
        stack: [
            {
                name: 'Vue.js',
                iconUrl: 'https://skillicons.dev/icons?i=vue' 
            },
            {
                name: 'Java Script',
                iconUrl: 'https://skillicons.dev/icons?i=js'
            },
            {
                name: 'TailwindCSS',
                iconUrl: 'https://skillicons.dev/icons?i=tailwindcss'
            }
        ]
    }
]
</script>

<template>
    <section >
        <GradientText
            text="Meus principais projetos"
            :colors="['#fff', '#5C10DB', '#fff']"
            :animation-speed="8"
            :show-border="false"
            class-name="flex p-4 text-4xl text-primary font-extrabold"
        />

        <div class="flex flex-col gap-20 space-y-6 lg:flex-row justify-evenly ">
            <div v-for="(item, index) in projects">
                <SpotlightCard 
                    class-name="custom-spotlight-card"
                    spotlight-color="rgba(255, 255, 255, 0.25)"
                >
                    <CardHeader>
                        <img
                            :src="item.preview"
                            alt=""
                            class="rounded-tl-md rounded-tr-md w-full z-40"
                        >
                    </CardHeader>
                    <CardContent class="m-4 gap-10 space-y-6">

                        <CardTitle class="text-4xl w-full justify-center text-center">
                            {{ item.title }}
                        </CardTitle>

                        
                        <CardDescription class="text-justify">
                            {{ item.description }}
                        </CardDescription>
                        <CardContent class="flex w-full justify-around">
                            <div v-for="i in item.stack">
                                <img :src="i.iconUrl" alt="stack">
                            </div>
                        </CardContent>
                        
                        <CardFooter class="flex gap-20">
                            <div class="w-full">
                                <a :href="item.webUrl" class="cursor-target w-full">
                                    <Button class="w-full">
                                        Pagina Web <Globe/>
                                    </Button>
                                </a>
                            </div>
                            <div class="w-full">
                                <a :href="item.githubUrl" class="cursor-target w-full">
                                    <Button class="w-full">
                                        GitHub <Github/>
                                    </Button>
                                </a>
                            </div>
                        </CardFooter>

                    </CardContent>
                </SpotlightCard>
            </div>            
        </div>
    </section>
</template>