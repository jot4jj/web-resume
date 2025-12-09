<script setup>
import GradientText from '@/animations/GradientText.vue';
import SpotlightCard from '@/animations/SpotlightCard.vue';

const stack = [
    {
        text: 'HTML',
        image: 'https://skillicons.dev/icons?i=html'
    },
    {
        text: 'CSS',
        image: 'https://skillicons.dev/icons?i=css'
    },
    {
        text: 'JavaScript',
        image: 'https://skillicons.dev/icons?i=js'
    },
    {
        text: 'Vue.js',
        image: 'https://skillicons.dev/icons?i=vue'
    },
    {
        text: 'TailwindCSS',
        image: 'https://skillicons.dev/icons?i=tailwind'
    },
    {
        text: 'Figma',
        image: 'https://skillicons.dev/icons?i=figma'
    },
    {
        text: 'Git',
        image: 'https://skillicons.dev/icons?i=git'
    },
    {
        text: 'Github',
        image: 'https://skillicons.dev/icons?i=github'
    }
]

</script>
<template>
    <section>
        <GradientText
            text="Tecnologias que utilizo"
            :colors="['#fff', '#5C10DB', '#fff']"
            :animation-speed="8"
            :show-border="false"
            class-name="flex p-4 text-4xl text-primary font-extrabold"
        />

        <SpotlightCard>
            <div class="justify-center grid grid-cols-2 md:grid-cols-4 lg:flex">
                <div v-for="item in stack" :key="item.text" class="m-6">
                    <div class="flex flex-col gap-2 items-center "> 
                        <img :src="item.image" :alt="item.text" class="w-20">
                        <p>{{ item.text }}</p>
                    </div>
                </div>
            </div>
        </SpotlightCard>

    </section>
</template>