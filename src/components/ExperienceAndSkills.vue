<template>
    <section class="text-white mt-18" id="skills">
        <div class="absolute right-0 top-[110rem] h-full w-full justify-end">
            <span class="flex opacity-20">
                <span class="w-16 h-32 rounded-l-full flex bg-primary blur-2xl"></span>
                <span class="w-16 h-32 rounded-r-full flex bg-[#f88fc2] blur-2xl mt-14"></span>
            </span>
        </div>
        <div class="md:grid md:grid-cols-2 gap-8 items-center py-8 px-4 xl:gap-16 xl:px-16">
            <div class="mt-4 md:mt-0 text-left flex flex-col z-10 h-full w-[80%]">
                <h2 class="text-4xl font-bold text-white text-left mb-4">My 
                    <span class="text-transparent bg-clip-text bg-gradient-to-r from-primary to-secondary">Skills</span>
                </h2>
                <div class="mt-8" v-for="skill in Skills" :key="skill.id">
                    <div class="flex items-end justify-between" data-aos="fade-right">
                        <h4 class="font-semibold text-white">
                            {{ skill.name }}
                        </h4>
                        <!-- <h3 class="text-2xl font-bold text-white">{{ skill.width }}</h3> -->
                    </div>
                    <!-- <div class="mt-2 h-1 w-full bg-[#131d30] rounded-full">
                        <div class="h-1 rounded-full bg-primary" :style="`width :${skill.width}`"></div>
                    </div> -->
                </div>
            </div>
            <div data-aos="flip-left">
                <h2 class="text-4xl font-bold text-white text-left mb-8 md:text-center md:mt-0 mt-8">My Experiences</h2>
                <div class="space-y-8 py-8" data-aos="fade-left">
                    <div v-for="element in Experinces" :key="element.id"
                    class="flex  items-center rounded-xl p-4 bg-[#111a3e] shadow-lg border border-[#1f1641]"
                    >
                    <div class="w-1/4">
                        <img src="https://img.icons8.com/ios-filled/100/ffffff/lawyer.png" alt="lawyer">
                    </div>
                    <div class="w-3/4 pl-4">
                        <h3 class="text-2xl font-semibold text-transparent bg-clip-text bg-gradient-to-r from-primary to-secondary">
                            {{ element.role }}
                        </h3>
                        <p class="text-white">{{ element.company }}</p>
                        <p class="text-white">{{ element.information }}</p>
                        <p class="text-white">{{ element.date }}</p>
                    </div>
                </div>
                </div>
            </div>
        </div>
    </section>
</template>
<script setup>
import { ref } from 'vue';
const Skills =ref([
    {
        id:1,
        name:'Laravel',
        // width:'85%'
    },
    {
        id:2,
        name:'Vue JS',
        // width:'70%'
    },
    {
        id:3,
        name:'React JS',
        // width:'98%'
    },
    {
        id:4,
        name:'Tailwind CSS',
        // width:'91%'
    },
    {
        id:5,
        name:'Bootstrap',
        // width:'91%'
    },
    {
        id:6,
        name:'Bekerja sama',
        // width:'91%'
    },
    {
        id:5,
        name:'Komunikasi',
        // width:'91%'
    },
]);

const Experinces =ref([
    {
        id:1,
        role:'Full Stack Developer',
        company:'Assyifa Islamic Philanthropy',
        information:'Membuat Sistem Manajemen untuk mengatur seputar Zakat, Ziswaf dan Wakaf menggunakan Laravel',
        date:'Desember 2022 - Januari 2023'
    },
    {
        id:2,
        role:'Full Stack Developer',
        company:'Dinas Komunikasi dan Informatika',
        information:'Project saat magang membuat Sistem Informasi Manajemen Rumah Sakit (SIMRS) RS Harmoni Kehidupan dengan menggunakan Laravel + Vue JS + Bootstrap + Midtrans',
        date:'Juli - September 2024'
    },
    {
        id:3,
        role:'Full Stack Developer',
        company:'Project tugas kampus',
        information:'Membuat project secara berkelompok dengan orang nya di bagi beberapa bagian kepengurusan, kami membuat project untuk sewa Photographer Pernikahan secara online agar bisa booking dari jarak jauh yang dinamakan Go Photo dengan menggunakan PHP',
        // date:'Mar 2022 - September 2023'
    },
    {
        id:4,
        role:'Full Stack Developer',
        company:'Project untuk penyusunan Tugas Akhir',
        information:'Membuat project untuk menyelesaikan Tugas Akhir dengan membuat sistem berbasis Chatbot AI Gemini menggunakan Laravel + React JS',
        // date:'Mar 2022 - September 2023'
    },
])
</script>
