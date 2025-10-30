<template >
    <section class="text-white mt-20" id="services">
        <div class="px-4 xl:pl-16">
            <h2 class="text-4xl font-bold text-white mb-4">My Skills</h2>
        </div>
        <div class="py-8 xl:px-16 px-4 sm:py-16 grid grid-cols-1 gap-6 pt-10 sm:grid-cols-2 md:gap-10 md:pt-12 lg:grid-cols-3">
            <div v-for="service in services" :key="service.id" data-aos="fade-up"
            class="px-8 py-12 rounded-xl bg-[#111a3e] shadow-lg border border-[#1f1641]"
            >
                <div class="mx-auto h-24 w-24 text-center xl:h-28 xl:w-28">
                    <div>
                        <img :src="service.icon" alt="service icon">
                    </div>
                </div>
                <div class="text-center">
                    <h3 class="pt-8 text-lg font-semibold text-transparent bg-clip-text bg-gradient-to-r from-primary to-secondary lg:text-xl">
                        {{ service.name }}
                    </h3>
                    <p class="text-grey pt-4 text-sm text-justify xgroup-hover:text-white md:text-base">
                        {{ service.description }}
                    </p>
                </div>
            </div>
        </div>
    </section>
</template>
<script setup>
import {ref} from 'vue';
const services =ref([
    {
        id:1,
        icon:'https://img.icons8.com/ios-filled/100/ffffff/google-code.png',
        name:'Full Stack Developer',
        description:'Full Stack Developer adalah seseorang di bidang teknologi informasi yang memiliki kemampuan untuk mengembangkan website di semua lapisan dari awal hingga akhir. Mereka memiliki pemahaman yang mendalam tentang pengembangan front-end, pengembangan back-end, serta pengetahuan tentang database.'
    },
    {
        id:2,
        icon:'https://img.icons8.com/external-vectorslab-glyph-vectorslab/100/fffeee/external-Technical-Writing-mobile-app-development-vectorslab-glyph-vectorslab.png',
        name:'Problem Solving',
        description:'Proses berpikir dan mencari solusi untuk mengatasi suatu masalah dengan cara yang efektif dan efisien.'
    },
    {
        id:3,
        icon:'https://img.icons8.com/?size=100&id=1476&format=png&color=FFFFFF',
        name:'HeidiSQL',
        description:'Sistem manajemen basis data relasional (RDBMS) yang bersifat open-source dan menggunakan SQL (Structured Query Language) untuk mengelola data.'
    },
    {
        id:4,
        icon:'https://img.icons8.com/?size=100&id=rY6agKizO9eb&format=png&color=000000',
        name:'Vue JS',
        description:'Framework JavaScript progresif yang digunakan untuk membangun antarmuka pengguna (UI) dan aplikasi web interaktif.'
    },
    {
        id:5,
        icon:'https://img.icons8.com/?size=100&id=58811&format=png&color=FFFFFF',
        name:'React JS',
        description:'Framework JavaScript yang digunakan untuk membangun antarmuka pengguna (UI) yang interaktif dan efisien, terutama dalam aplikasi berbasis Single Page Application (SPA). Sebenarnya sama saja seperti Vue JS'
    },
    {
        id:6,
        icon:'https://img.icons8.com/?size=100&id=hUvxmdu7Rloj&format=png&color=000000',
        name:'Laravel',
        description:'Framework PHP yang digunakan untuk membangun aplikasi web dengan struktur yang rapi, aman, dan efisien. Bisa digabungkan dengan Vue JS / React JS jika digabung maka Laravel digunakan sebagai Backend'
    },
    {
        id:7,
        icon:'https://img.icons8.com/?size=100&id=4PiNHtUJVbLs&format=png&color=000000',
        name:'Tailwind CSS',
        description:'Framework CSS berbasis utility-first yang memungkinkan pengembang membangun desain antarmuka dengan cepat dan fleksibel. Biasa nya saat project digunakan untuk CSS di Vue JS / React JS'
    },
    {
        id:8,
        icon:'https://img.icons8.com/?size=100&id=PndQWK6M1Hjo&format=png&color=000000',
        name:'Bootstrap',
        description:'Framework CSS yang digunakan untuk membangun antarmuka web yang responsif dan cepat dengan komponen siap pakai. Biasa nya saat project digunakan untuk Laravel'
    },
    {
        id:9,
        icon:'https://img.icons8.com/?size=100&id=uY6QHPV8g5bd&format=png&color=000000',
        name:'Google Fonts',
        description:'Layanan gratis dari Google yang menyediakan berbagai jenis font web yang dapat digunakan dalam desain dan pengembangan website.'
    },
    ])
</script>

