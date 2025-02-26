<script setup>
import { ref, computed } from 'vue';
import wb_yhsmovies from '@/assets/react_movie_app.png';
import wb_klassrum from '@/assets/klassrum.jpg';
import mb_dactest from '@/assets/project.png';
import wb_memo from '@/assets/memo.png';
import ds_fiber from '@/assets/ml_fiber.jpg';
import ds_credits from '@/assets/ml_credits.jpeg';
import ds_crimes from '@/assets/ml_crimes.jpg';
import ds_energy from '@/assets/ml_energy.jpeg'; 

const Projects = ref([
    {
        id: 1,
        category: 'WEB',
        image: wb_yhsmovies,
        title: 'Y\'Movies',
        description: 'Y\'Movies est une application web permettant de rechercher et de visualiser des informations sur les films avec une expérience utilisateur optimale.',
        technologies: ['react.js', 'tailwindcss'],
        gitURL: 'https://github.com/Yehoshua517/sirius-frontend',
        webURL: 'https://sirius-ftd.vercel.app/'
    },
    {
        id: 2,
        category: 'DATA SCIENCE',
        image: ds_fiber,
        title: 'FTTH IA CHALLENGE 2024',
        description: 'Développer une solution de machine learning pour prédire l’adoption de la fibre optique à domicile (FTTH) dans différentes régions du Togo.',
        technologies: ['Python', 'Mosaiks'],
        gitURL: '',
        webURL: 'https://www.kaggle.com/code/aaaml007/zindi-tg-ftth-solution-by-yehoshua'
    },
    {
        id: 3,
        category: 'DATA SCIENCE',
        image: ds_credits,
        title: 'APPROBATION DES CARTES',
        description: 'Développer un modèle de machine learning pour prédire l’approbation d\'une carte de crédit d’un client en fonction de ses informations personnelles.',
        technologies: ['Python', 'ML', 'Supervised learning'],
        gitURL: '',
        webURL: 'https://www.datacamp.com/datalab/w/7fad976b-4281-4950-b0c1-a76d705574f3/edit'
    },
    {
        id: 4,
        category: 'MOBILE',
        image: mb_dactest,
        title: 'DacTest',
        description: 'DacTest est une mini-application mobile de networking. Elle permet de mettre en relation des profils d\'utilisateurs d\'un même secteur d\'activité',
        technologies: ['SQFlite', 'BLoC', 'Flutter'],
        gitURL: 'https://github.com/Yehoshua517/DacTest',
        webURL: ''
    },
    {
        id: 5,
        category: 'WEB',
        image: wb_klassrum,
        title: 'API Klassrum',
        description: 'l\'API RESTful de Klassrum est une API pour une application de gestion de salles de classe. Elle permet de gérer les salles, les séances de cours et les étudiants.',
        technologies: ['Express/Node.js', 'MongoDB', '50%'],
        gitURL: 'https://github.com/Yehoshua517/klassrum_backend',
        webURL: 'https://klassrum.onrender.com/'
    },
    {
        id: 6,
        category: 'WEB',
        image: wb_memo,
        title: 'FlashMemo Edge',
        description: 'FlashMemo est une extension web qui vous permet de sauvegarder vos notes et les retrouver facilement en un click. Simple, rapide et efficace.',
        technologies: ['Javascript', 'styled-components'],
        gitURL: '',
        webURL: ''
    },
    // {
    //     id: 7,
    //     category: 'DATA SCIENCE',
    //     image: ds_crimes,
    //     title: 'ANALYSE DES CRIMES A LOS ANGELES',
    //     description: 'Analyser les données des crimes à Los Angeles pour en extraire des informations utiles et les visualiser sous forme de graphiques.',
    //     technologies: ['Python', 'Unsupervised learning'],
    //     gitURL: '',
    //     webURL: 'https://www.datacamp.com/datalab/w/a921b278-0eaf-4406-b5f1-cc595b5a2061/edit'
    // },
    // {
    //     id: 8,
    //     category: 'DATA SCIENCE',
    //     image: ds_energy,
    //     title: 'PREDICTION DE LA CONSOMMATION D\'ENERGIE',
    //     description: 'Développer une solution de machine learning pour prédire la consommation d\'énergie d\'un bâtiment en fonction de ses caractéristiques.',
    //     technologies: ['R', 'ML'],
    //     gitURL: '',
    //     webURL: 'https://www.datacamp.com/datalab/w/70d22f5f-85ed-44da-a03f-404fe7dab5e1/edit'
    // }
]);

const selectedCategory = ref('ALL');
const filteredProjects = computed(() => {
    if (selectedCategory.value === 'ALL') {
        return Projects.value;
    }
    return Projects.value.filter(project => project.category.toLocaleUpperCase() === selectedCategory.value.toLocaleUpperCase());
})
</script>

<template>
    <section class="text-white mt-20" id="projects">
        <div class="px-4 xl:pl-16">
            <div class="mb-4 md:flex md:justify-between xl:pr-16">
                <h2 class="text-4xl font-bold text-white"> Projets récents</h2>
                <div class="flex space-x-4 mb-4 mt-5 md:mt-0">
                    <button class="hover:text-primary" v-for="category in ['ALL', 'WEB', 'MOBILE', 'DATA SCIENCE']"
                        :key="category" @click="() => selectedCategory = category">
                        {{ category }}
                    </button>
                </div>
            </div>
            <ul class="px-4 sm:py-16 xl:pr-16 grid grid-cols-1 gap-6 pt-10 sm:grid-cols-2 md:gap-10 md:pt-12 lg:grid-cols-3"
                data-aos="fade-right">
                <div v-for="project in filteredProjects" :key="project.id">
                    <div class="h-52 md:h-[24rem] rounded-t-xl relative group"
                    :style="{ backgroundImage: 'url(' + project.image + ')', backgroundSize: 'cover' }">                    
                    <div class="overlay items-center justify-center absolute top-0 left-0 w-full h-full bg-[#181818] bg-opacity-0
                    hidden group-hover:flex group-hover:bg-opacity-80 transition-all duration-500
                    ">
                        <a class="h-14 w-14 mr-2 border-2 relative rounded-full border-[#ADB7BE] hover:border-white group/link"
                            :href="project.gitURL" v-if="project.gitURL.trim() !== ''" target="_blank"> <svg xmlns="http://www.w3.org/2000/svg" fill="none"
                                viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" aria-hidden="true"
                                data-slot="icon"
                                class="h-10 w-10 text-[#ADB7BE] absolute top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2  cursor-pointer group-hover/link:text-white">
                                <path stroke-linecap="round" stroke-linejoin="round"
                                    d="M17.25 6.75 22.5 12l-5.25 5.25m-10.5 0L1.5 12l5.25-5.25m7.5-3-4.5 16.5">
                                </path>
                            </svg></a><a
                            class="h-14 w-14 border-2 relative rounded-full border-[#ADB7BE] hover:border-white group/link"
                            :href="project.webURL" v-if="project.webURL.trim() !== ''" target="_blank"> <svg xmlns="http://www.w3.org/2000/svg" fill="none"
                                viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" aria-hidden="true"
                                data-slot="icon"
                                class="h-10 w-10 text-[#ADB7BE] absolute top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2  cursor-pointer group-hover/link:text-white">
                                <path stroke-linecap="round" stroke-linejoin="round"
                                    d="M2.036 12.322a1.012 1.012 0 0 1 0-.639C3.423 7.51 7.36 4.5 12 4.5c4.638 0 8.573 3.007 9.963 7.178.07.207.07.431 0 .639C20.577 16.49 16.64 19.5 12 19.5c-4.638 0-8.573-3.007-9.963-7.178Z">
                                </path>
                                <path stroke-linecap="round" stroke-linejoin="round"
                                    d="M15 12a3 3 0 1 1-6 0 3 3 0 0 1 6 0Z"></path>
                            </svg></a>
                    </div>
                </div>
                <div class="text-white rounded-b-xl mt-3 bg-[#111a3e] shadow-lg border border-[#1f1641] py-6 px-4">
                    <h3 class="text-lg font-semibold uppercase lg:text-xl"> {{ project.title }}</h3>
                    <p class="text-[#ADB7BE]">{{ project.description }}</p>
                    <div class="flex flex-wrap p-2.5">
                        <div v-for="technology in project.technologies" :key="technology" class="text-center ml-1 mt-1 rounded-3xl bg-[#111827]"
                        style="box-shadow: 0 4px 30px rgba(0, 0, 0, 0.1); border: 1px solid #111827;backdrop-filter: blur(9px);-webkit-backdrop-filter: blur(9px);"
                        >
                            <p class="px-2 py-1">{{ technology }}</p>
                        </div>
                    </div>
                </div>
                </div>
            </ul>
        </div>
    </section>
</template>