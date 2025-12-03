<script setup>
import {
    Card,
    CardAction,
    CardDescription,
    CardHeader,
    CardTitle
} from './ui/card';
import GradientText from '@/animations/GradientText.vue';

const journey = [
    {
        title: 'Estágio em Desenvolvimento de Sistemas',
        location: 'EEEP Jaime da Cunha Rebouças',
        period: 'Agosto - Dezembro',
        description: 'Estágio com foco em aprendizado, aplicando conhecimentos principalmente de Vue.js, Tailwind CSS'
    },
    {
        title: 'Estágio em Desenvolvimento de Sistemas',
        location: 'EEEP Jaime da Cunha Rebouças',
        period: 'Agosto - Dezembro',
        description: 'Estágio com foco em aprendizado, aplicando conhecimentos principalmente de Vue.js, Tailwind CSS'
    },
]
</script>

<template>
<section>
    <h2 class="flex p-4 text-4xl text-primary font-extrabold">
        <GradientText
            text="Minha Jornada de aprendizado"
            :colors="['#ffaa40', '#9c40ff', '#ffaa40']"
            :animation-speed="6"
            :show-border="false"
        />
    </h2>

    <div class="flex justify-evenly gap-10">
        <div v-for="(item, index) in journey">
            <Card>
                <CardHeader>
                    <CardTitle>
                        {{ item.title }}
                    </CardTitle>
                </CardHeader>

                <CardDescription class="px-4">
                    {{ item.location }} || {{ item.description }}
                </CardDescription>
            </Card>
        </div>
    </div>
</section>
</template>