<script setup>
import {
    Card,
    CardAction,
    CardDescription,
    CardHeader,
    CardTitle
} from './ui/card';
import GradientText from '@/animations/GradientText.vue';
import SpotlightCard from '@/animations/SpotlightCard.vue';

const journey = [
    {
        title: 'Primeiro Contato com Programação',
        location: 'EEEP Jaime da Cunha Rebouças',
        period: 'Agosto - Dezembro',
        description: 'Meu primeiro contato com programação aconteceu em 2022, quando tive minhas primeiras experiências com HTML e CSS. A partir desse momento, passei a me interessar cada vez mais pela área e decidi ingressar no curso técnico de Desenvolvimento de Sistemas para aprofundar meus conhecimentos.'
    },
    {
        title: 'Curso técnico',
        location: 'EEEP Jaime da Cunha Rebouças',
        period: 'Agosto - Dezembro',
        description: 'Ao iniciar o curso, fui introduzido aos fundamentos da lógica de programação e, em seguida, estudei minha primeira linguagem: Python. No segundo semestre de 2024, começamos a explorar Programação Web e Programação Orientada a Objetos, ampliando minha base técnica e meu entendimento sobre desenvolvimento de software.'
    },
    {
        title: 'Aprofundamento',
        location: 'EEEP Jaime da Cunha Rebouças',
        period: 'Agosto - Dezembro',
        description: 'Entre o segundo semestre de 2024 e meados de 2025, busquei expandir ainda mais meu conhecimento por meio de cursos externos. Foi nesse período que tive contato com minha primeira linguagem de programação voltada ao desenvolvimento web: JavaScript. Esse aprofundamento me motivou a estudar de forma contínua e começar a construir projetos mais sólidos.'
    },
    {
        title: 'Estágio e primeiros projetos',
        location: 'EEEP Jaime da Cunha Rebouças',
        period: 'Agosto - Dezembro',
        description: 'No segundo semestre de 2025, iniciei meu estágio supervisionado obrigatório, oferecido pela EEEP. Durante essa experiência, consegui consolidar tudo o que havia aprendido até então e aplicar na prática, desenvolvendo novos projetos e adquirindo diversas habilidades adicionais, tanto técnicas quanto profissionais.'
    },
]

</script>

<template>
<section>
    <GradientText
        text="Minha jornada de aprendizado"
        :colors="['#fff', '#5C10DB', '#fff']"
        :animation-speed="8"
        :show-border="false"
        class-name="flex p-4 text-4xl text-primary font-extrabold"
    />

    <div class="justify-evenly gap-10 grid grid-cols-1 lg:grid-cols-2">
        <div v-for="(item, index) in journey">
            <SpotlightCard class="p-4 ">

                <CardHeader>
                    <CardTitle>
                        {{ item.title }}
                    </CardTitle>
                </CardHeader>

                <CardDescription>
                    {{ item.description }}
                </CardDescription>

            </SpotlightCard>
        </div>
    </div>
</section>
</template>