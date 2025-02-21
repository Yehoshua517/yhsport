<script setup>
import { ref } from 'vue';

// Data for the contact form
const name = ref('');
const email = ref('');
const subject = ref('');
const message = ref('');
const dateOfSubmission = ref(new Date(Date.now()).toLocaleString());

// Send the message
const sendMessage = async () => {
    const form = document.getElementById('contact-form');
    const formData = new FormData(form);
    
    fetch('https://formspree.io/f/xpwqbkgv', {
        method: 'POST',
        body: formData,
        headers: {
            'Accept': 'application/json'
        }
    })
    .then((response) => {
        if (response.ok) {
            alert('Email sent successfully!');
            form.reset(); // Clear the form
        } else {
            alert('Failed to send email. Please try again.');
        }
    })
    .catch((error) => {
        console.error('Error:', error);
    });
}

</script>

<template>
    <section class="text-white mt-20" id="contact">
        <h2 class="text-4xl font-bold text-white text-left mb-4 px-4 xl:pl-16">Connectons-nous</h2>
        <div class="grid md:grid-cols-2 gap-4 relative px-4 xl:px-16 mt-8" data-aos="zoom-in-up">
            <div>
                <p class="text-[#adb7be]">Que vous souhaitiez discuter de collaborations, poser des questions, partager des idées ou simplement échanger,<br/> 
                    c'est ici que tout commence. N'hésitez pas à me contacter via les réseaux sociaux, par e-mail ou en laissant un message directement ici. 
                    Je suis toujours ravi de découvrir de nouvelles perspectives et de rencontrer des esprits créatifs. <br/> Alors, prêt à échanger ? 👋
                </p>
                <div class="col-lg-4 col-md-4 mb-lg-0 mt-5">
                    <div class="flex mb-10 items-center">
                        <div class="p-2"
                            style="background: #111a3e; width: 50px;height: 46px; display: flex;justify-content: center; border-radius: 50%;
                        overflow: hidden;border: 1px solid#111a3e;backdrop-filter: blur(9px);-webkit-backdrop-filter: blur(9px);">
                            <img src="https://img.icons8.com/metro/50/ffffff/new-post.png" alt="new-post" class="w-6">
                        </div>
                        <div class="ml-5 text-white">
                            <h4>Email</h4>
                            <p>jackjosue517@gmail.com</p>
                        </div>
                    </div>
                    <div class="flex mb-10 items-center">
                        <div class="p-2"
                            style="background: #111a3e; width: 50px;height: 46px; display: flex;justify-content: center; border-radius: 50%;
                        overflow: hidden;border: 1px solid#111a3e;backdrop-filter: blur(9px);-webkit-backdrop-filter: blur(9px);">
                            <img src="https://img.icons8.com/ios-filled/50/ffffff/phone.png" alt="phone" class="w-6">
                        </div>
                        <div class="ml-5 text-white">
                            <h4>Phone</h4>
                            <p>+228 91 11 25 41</p>
                        </div>
                    </div>
                    <div class="flex mb-10 items-center">
                        <div class="p-2"
                            style="background: #111a3e; width: 50px;height: 46px; display: flex;justify-content: center; border-radius: 50%;
                        overflow: hidden;border: 1px solid#111a3e;backdrop-filter: blur(9px);-webkit-backdrop-filter: blur(9px);">
                            <img src="https://img.icons8.com/ios-filled/50/ffffff/linkedin.png" alt="linkedin"
                                class="w-6">
                        </div>
                        <div class="ml-5 text-white">
                            <h4>LinkedIn</h4>
                            <p>@yehoshua1</p>
                        </div>
                    </div>
                </div>
            </div>
            <div
            style="background: #111a3e; width: 100%;height: 100%; border-radius: 20px;
            overflow: hidden;border: 1px solid #111a3e;backdrop-filter: blur(9px);-webkit-backdrop-filter: blur(9px);">
            <form class="flex flex-col p-4" data-aos="zoom-in-up" action="https://formspree.io/f/xpwqbkgv" method="POST" id="contact-form">
                <div class="mb-6">
                    <label for="name" class="text-white block mb-2 text-sm font-medium">Name</label>
                    <input type="text" id="name" class="bg-[#111827] placeholder:[#9CA2A9] text-gray-100 text-sm rounded-lg block w-full p-2.5"
                    placeholder="Louise Dupont" name="name" v-model="name">
                </div>
                <div class="mb-6">
                    <label for="email" class="text-white block mb-2 text-sm font-medium">Email</label>
                    <input type="email" id="email" class="bg-[#111827] placeholder:[#9CA2A9] text-gray-100 text-sm rounded-lg block w-full p-2.5"
                    placeholder="Email@gmail.com" name="email" v-model="email">
                </div>
                <div class="mb-6">
                    <label for="subject" class="text-white block mb-2 text-sm font-medium">Sujet</label>
                    <input type="text" id="subject" class="bg-[#111827] placeholder:[#9CA2A9] text-gray-100 text-sm rounded-lg block w-full p-2.5"
                    placeholder="Sujet" name="subject" v-model="subject">
                </div>
                <div class="mb-6">
                    <label for="message" class="text-white block mb-2 text-sm font-medium">Message</label>
                    <textarea id="message" class="bg-[#111827] placeholder:[#9CA2A9] text-gray-100 text-sm rounded-lg block w-full p-2.5"
                    placeholder="Discuter de... " name="message" v-model="message"></textarea>
                </div>
                <button class="z-1 w-[100%!important] px-6 md:px-7 py-3 rounded-full sm:w-max flex justify-center text-white bg-primary border-2 border-transparent"
                    @click.prevent="sendMessage">
                    Envoyer message
                </button>
            </form>
        </div>
        <div class="bg-gradient-to-tr opacity-25 from-[#570cac] to-primary blur-2xl h-20 w-80 z-0 absolute -top-1/2 -left-4 transform -translate-x-2/3 
        -translate-1/2
        "></div>
        </div>
    </section>
</template>