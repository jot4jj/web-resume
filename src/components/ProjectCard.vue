<script setup>
import {
    Card,
    CardAction,
    CardDescription,
    CardHeader,
    CardTitle,
    CardContent
} from './ui/card';


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
        <h2 class="flex justify-center p-4 text-4xl text-primary font-extrabold">Meus principais Projetos</h2>

        <div class="flex gap-10 justify-evenly">
            <div v-for="(item, index) in projects">
                <Card class="p-4 shadow-2xl">
                    <CardHeader>
                        <CardTitle class="text-4xl"> {{ item.title }} </CardTitle>
                    </CardHeader>

                    <CardDescription> {{ item.description }} </CardDescription>
                    
                    <img
                        :src="item.preview"
                        alt=""
                        class="rounded-md mx-2"
                    >
                    <CardContent class="flex justify-around">
                        <div v-for="i in item.stack">
                            <img :src="i.iconUrl" alt="stack">
                        </div>
                    </CardContent>
                </Card>
            </div>            
        </div>
    </section>
</template>