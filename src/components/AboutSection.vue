<script setup>
import { ref } from 'vue';

const education = ref([
    {
        id:1,
        School:'Ecole Polytechnique de Lome (UL)',
        program:'Génie Logiciel',
        year:'2021 – 2024'
    },
    {
        id:2,
        School:'Notre Dame de L’église (IS)',
        program:'Série scientifique (C4)',
        year:'2017 – 2021'
    },
    {
        id:3,
        School:'Abel (GS)',
        program:'Collège',
        year:'2013 – 2017'
    },
    {
        id:4,
        School:'San Francisco',
        program:'Primaire',
        year:'2007 – 2013'
    }
])
</script>

<template>
    <section id="about">
        <div class="absolute z-0 top-[93rem] inset-x-0 h-64 flex items-start">
            <div class="h-24 w-64 bg-gradient-to-br from-primary via-secondary blur-2xl to-[#570cac] opacity-20"></div>
        </div>
        <div class="md:grid md:grid-cols-2 gap-8 items-center py-8 px-4 xl:gap-16 sm:py-16 xl:px-16 z-1">
            <div data-aos="flip-right">
                <h2 class="text-4xl font-bold text-white text-left mb-8">Mon éducation</h2>
                <div class="space-y-8 py-8">
                    <div v-for="element in education" :key="element.id"
                    class="flex items-center md:w-[80%] w-full rounded-xl bg-[#111a3e] shadow-lg border border-[#1f1641]"
                    >
                        <div class="w-1/4">
                            <img src="https://img.icons8.com/ios-glyphs/60/ffffff/graduation-cap--v1.png" alt="graduation-cap--v1">
                        </div>
                        <div class="w-3/4 pl-4">
                            <h3 class="text-2xl font-semibold uppercase text-transparent bg-clip-text bg-gradient-to-r from-primary to-secondary lg:text-xl">
                                {{ element.School }}
                            </h3>
                            <p class="text-white">{{ element.program }}</p>
                            <p class="text-white">{{ element.year }}</p>
                        </div>
                    </div>
                </div>
            </div>

            <div class="mt-4 md:mt-0 text-left flex flex-col z-10 h-full" data-aos="flip-right">
                <h2 class="text-4xl font-bold text-white md:text-center text-left mb-4">
                    <span class="text-transparent bg-clip-text bg-gradient-to-r from-primary to-secondary">À propos</span>
                    de Moi
                </h2>
                <p class="text-base lg:text-lg mt-8 py-8 text-white"> Je m'appelle Kodjo Josué AYITEY (Jak), et je suis passionné par la technologie, l'innovation 
                    et la création de solutions qui repoussent les limites du possible. Que ce soit à travers le développement web, 
                    la conception d'applications mobiles, ou l'intelligence artificielle, j'aime transformer des idées en réalité 
                    et résoudre des problèmes complexes grâce à la puissance du code et de la créativité.
                </p>
                <div class="grid grid-cols-3 gap-4 max-w-lg pt-8">
                    <div class="text-center rounded-xl bg-[#111a3e] shadow-lg border border-[#1f1641] p-3">
                        <h3 class="text-white font-bold text-xl sm:text-2xl lg:text-3xl">+5</h3>
                        <p class="text-sm sm:text-base text-gray-300">Avis positifs</p>
                    </div>
                    <div class="text-center rounded-xl bg-[#111a3e] shadow-lg border border-[#1f1641] p-3">
                        <h3 class="text-white font-bold text-xl sm:text-2xl lg:text-3xl">+10</h3>
                        <p class="text-sm sm:text-base text-gray-300">Projets</p>
                    </div>

                    <div class="text-center rounded-xl bg-[#111a3e] shadow-lg border border-[#1f1641] p-3">
                        <h3 class="text-white font-bold text-xl sm:text-2xl lg:text-3xl">+7</h3>
                        <p class="text-sm sm:text-base text-gray-300"> Année(s) d'Expérience</p>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>