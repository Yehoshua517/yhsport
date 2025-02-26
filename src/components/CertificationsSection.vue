<script setup>
import { ref } from 'vue'
import efset from '@/assets/efset.png'
import zindi from '@/assets/zindi.png'
import hacker from '@/assets/hacker.png'
import cplus from '@/assets/cplus.jpg'
import figma from '@/assets/figma.jpg'
import reply from '@/assets/reply.png'
import full from '@/assets/full.jpg'

const certifications = ref([
    {
        id: 1,
        name: 'RCC',
        description: '21 mars 2024',
        img: reply,
        url: ''
    },
    {
        id: 2,
        name: 'Anglais',
        description: '15 juillet 2024',
        img: efset,
        url: ''
    },
    {
        id: 3,
        name: 'IA',
        description: '23 juin 2024',
        img: zindi,
        url: ''
    },
    {
        id: 4,
        name: 'PYTHON',
        description: '03 juillet 2024',
        img: hacker,
        url: ''
    },
    {
        id: 5,
        name: 'Node.js',
        description: '19 février 2024',
        img: full,
        url: ''
    },
    {
        id: 6,
        name: 'C++',
        description: '04 avril 2023',
        img: cplus,
        url: ''
    },
    {
        id: 7,
        name: 'Figma',
        description: '04 mai 2023',
        img: figma,
        url: ''
    },
])
</script>

<template>
    <section id="certifications" class="px-4 xl:px-16 mt-20">
        <div data-aos="flip-right">
            <h2 class="text-4xl font-bold text-white text-left mb-8">Certifications</h2>
            <div class="space-y-8 py-8">
                <div v-for="element in certifications" :key="element.id"
                class="flex items-center md:w-[100%] w-full rounded-xl bg-[#111a3e] shadow-lg border border-[#1f1641]"
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