<script setup>
import { ref } from 'vue'
import efset from '@/assets/efset.png'
import zindi from '@/assets/zindi.png'
import hacker from '@/assets/hacker.png'

const certifications = ref([
    {
        id: 1,
        name: 'Test de niveau d\'anglais',
        description: '15 juillet 2024',
        img: efset,
        url: 'https://bit.ly/46ex9yH'
    },
    {
        id: 2,
        name: 'TOGO FIBER OPTICS UPTAKE PREDICTION CHALLENGE',
        description: '23 juin 2024',
        img: zindi,
        url: 'https://bit.ly/3y5AIKQ'
    },
    {
        id: 3,
        name: 'Les bases de PYTHON sur HACKER RANK',
        description: '03 juillet 2024',
        img: hacker,
        url: 'https://bit.ly/4673SG2'
    },
])
</script>

<template>
    <section id="certifications" class="px-4 xl:px-16 mt-20">
        <div data-aos="flip-right">
            <h2 class="text-4xl font-bold text-white text-left mb-8">Certifications</h2>
            <div class="space-y-8 py-8">
                <div v-for="element in certifications" :key="element.id"
                class="flex items-center md:w-[80%] w-full rounded-xl bg-[#111a3e] shadow-lg border border-[#1f1641]"
                >
                    <div class="w-4/5">
                        <img :src="element.img" alt="graduation-cap--v1">
                    </div>
                    <div class="w-3/4 pl-8">
                        <h3 class="text-2xl font-semibold uppercase text-transparent bg-clip-text bg-gradient-to-r from-primary to-secondary lg:text-xl">
                            {{ element.name }}
                        </h3>
                        <p class="text-white">{{ element.description }}</p>
                        <p class="text-blue-600">{{ element.url }}</p>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>