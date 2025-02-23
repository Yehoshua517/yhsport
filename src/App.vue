<script setup>
import { defineAsyncComponent } from 'vue';

// Import components Asynchronously
const NavBar = defineAsyncComponent(() => import('@/components/NavBar.vue'));
const HeroSection = defineAsyncComponent(() => import('@/components/HeroSection.vue'));
const ServicesSection = defineAsyncComponent(() => import('@/components/ServicesSection.vue'));
const AboutSection = defineAsyncComponent(() => import('@/components/AboutSection.vue'));
const ExperienceAndSkills = defineAsyncComponent(() => import('@/components/ExperienceAndSkills.vue'));
const LatestProjectSection = defineAsyncComponent(() => import('@/components/LatestProjectSection.vue'));
const ContactSection = defineAsyncComponent(() => import('@/components/ContactSection.vue'));
const TestimonialsSection = defineAsyncComponent(() => import('@/components/TestimonialsSection.vue'));
const Footer = defineAsyncComponent(() => import('@/components/Footer.vue'));
const BackToTop = defineAsyncComponent(() => import('@/components/BackToTop.vue'));
const CertificationsSection = defineAsyncComponent(() => import('@/components/CertificationsSection.vue'));
</script>

<template>
    <div class="bg-[#111827] min-h-screen">
        <!-- Wrap components in Suspense to handle loading -->
        <Suspense>
            <template #default>
                <!-- Wrap all components inside a single root element -->
                <div>
                    <NavBar />
                    <HeroSection />
                    <ServicesSection />
                    <AboutSection />
                    <ExperienceAndSkills />
                    <CertificationsSection />
                    <LatestProjectSection />
                    <ContactSection />
                    <TestimonialsSection />
                    <Footer />
                    <BackToTop />
                </div>
            </template>

            <template #fallback>
                <div class="flex justify-center items-center min-h-screen">
                    <LoadingSpinner />
                </div>
            </template>
        </Suspense>
    </div>
</template>

<style>
*{
    scrollbar-width: thin;
    scrollbar-color: #111827 #f1f1f1;
}
</style>