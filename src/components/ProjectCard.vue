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
import ScrollFloat from '@/animations/ScrollFloat.vue';


const projects = [
    {
        title: 'Pokédex com Vue.js e TailwindCSS',
        description: 'Uma Pokédex interativa desenvolvida com Vue 3, TailwindCSS, Axios e a PokéAPI, permitindo buscar Pokémon por nome, tipo ou geração. O projeto foi criado com foco em boas práticas de componentização (Atomic Design) e uma UI responsiva e limpa',
        preview: '/img/preview-pokedex.png',
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
    },
    {
        title: 'Mapa interativo com Leaflet.js',
        description: 'Um mapa interativo desenvolvido com Vue 3, Leaflet e TailwindCSS, permitindo visualizar pontos, áreas e informações geográficas em tempo real. O projeto destaca boas práticas de componentização, UI responsiva e integração fluida com dados geoespaciais.',
        preview: '/img/preview-map.png',
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
        <h2 class="flex p-4 text-4xl text-primary font-extrabold">
            <ScrollFloat
                children="Meus principais projetos"
                :animation-duration="animationDuration"
                :ease="ease"
                :scroll-start="scrollStart"
                :scroll-end="scrollEnd"
                :stagger="stagger"
                :container-class-name="containerClassName"
                :text-class-name="textClassName"
                :scroll-container-ref="{ current: containerRef }"
                :key="rerenderKey"
            />
        </h2>

        <div class="flex gap-10 justify-evenly">
            <div v-for="(item, index) in projects">
                <Card class="shadow-2xl">
                    <CardHeader>
                        <img
                            :src="item.preview"
                            alt=""
                            class="rounded-tl-md rounded-tr-md w-full"
                        >
                    </CardHeader>
                    <CardContent class="m-4 gap-10 space-y-6">

                        <CardTitle class="text-4xl w-full justify-center text-center">
                            {{ item.title }}
                        </CardTitle>

                        <CardContent class="flex w-full justify-around">
                            <div v-for="i in item.stack">
                                <img :src="i.iconUrl" alt="stack">
                            </div>
                        </CardContent>

                        <CardDescription class="text-justify">
                            {{ item.description }}
                        </CardDescription>
                        
                        <CardFooter class="flex justify-around">

                        </CardFooter>

                    </CardContent>
                </Card>
            </div>            
        </div>
    </section>
</template>