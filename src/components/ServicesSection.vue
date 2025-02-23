<script setup>
    import { ref } from 'vue';
    const services = ref([
        {
            id: 1,
            icon: 'https://img.icons8.com/ios-filled/100/ffffff/google-code.png',
            name: 'DEVELOPPEMENT WEB',
            description: 'Créez des sites web dynamiques et performants pour offrir une expérience utilisateur exceptionnelle.'
        },
        {
            id: 2,
            icon: 'https://img.icons8.com/ios-filled/100/ffffff/online-support.png',
            name: 'DEVELOPPEMENT MOBILE',
            description: 'Concevez des applications mobiles intuitives et innovantes pour répondre aux besoins des utilisateurs modernes.'
        },
        {
            id: 3,
            icon: 'https://img.icons8.com/ios-filled/100/ffffff/windows10-personalization.png',
            name: 'DESIGN GRAPHIQUE',
            description: 'Donnez vie à vos idées avec des designs visuellement percutants qui captivent et inspirent.'
        },
        {
            id: 4,
            icon: 'https://img.icons8.com/ios-filled/100/ffffff/artificial-intelligence.png',
            name: 'INTELLIGENCE ARTIFICIELLE',
            description: 'Développez des solutions d\'IA sur mesure pour automatiser vos processus, analyser des données et prendre des décisions intelligentes.'
        },
    ])
</script>

<template>
    <section class="text-white mt-20" id="services">
        <div class="px-4 xl:pl-16">
            <h2 class="text-4xl font-bold text-white mb-4">Mes Services</h2>
        </div>
        <div class="py-8 xl:px-16 px-4 sm:py-16 grid grid-cols-1 gap-6 pt-10 sm:grid-cols-2 md:gap-10 md:pt-12 lg:grid-cols-3">
            <div v-for="service in services" :key="service.id" data-aos="fade-up" class="px-8 py-12 rounded-xl bg-[#111a3e] shadow-lg border border-[#1f1641]">
                <div class="mx-auto h-24 text-center xl:h-28 xl:w-28">
                    <img :src="service.icon" alt="service icon">
                </div>

                <div class="text-center">
                    <h3 class="pt-8 text-lg font-semibold uppercase text-transparent bg-clip-text bg-gradient-to-r from-primary to-secondary lg:text-xl">
                        {{ service.name }}
                    </h3>
                    <p class="text-grey pt-4 text-sm group-hover:text-white md:text-base">
                        {{ service.description }}
                    </p>
                </div>
            </div>
        </div>
    </section>
</template>