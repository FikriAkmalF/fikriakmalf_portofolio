<template>
  <section class="text-white mt-20" id="experiences">
    <div class="absolute right-0 top-[110rem] h-full w-full justify-end">
      <span class="flex opacity-20">
        <span class="w-16 h-32 rounded-l-full flex bg-primary blur-2xl"></span>
        <span class="w-16 h-32 rounded-r-full flex bg-[#f88fc2] blur-2xl mt-14"></span>
      </span>
    </div>

    <div class="mx-auto max-w-7xl py-8 px-4 xl:px-16">
      <h2 class="text-4xl font-bold text-white text-center mb-10">My Experiences</h2>

      <div class="text-justify sm:grid sm:grid-cols-2 gap-8 py-8">
        <div
          v-for="element in Experinces"
          :key="element.id"
          class="flex items-center rounded-xl p-4 bg-[#111a3e] shadow-lg border border-[#1f1641] transition-all duration-300 hover:scale-[1.01] hover:shadow-2xl hover:border-primary mb-8 sm:mb-0"
        >
          <div class="w-1/4 flex-shrink-0">
            <img
              src="https://img.icons8.com/ios-filled/100/ffffff/lawyer.png"
              alt="lawyer"
            />
          </div>
          <div class="w-3/4 pl-4">
            <h3
              class="text-2xl font-semibold text-transparent bg-clip-text bg-gradient-to-r from-primary to-secondary"
            >
              {{ element.role }}
            </h3>
            <p class="text-white">{{ element.company }}</p>
            <p class="text-white mt-2">{{ element.information }}</p>
            <p class="text-white mt-1">{{ element.date }}</p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from "vue";
import AOS from "aos";
import "aos/dist/aos.css";
AOS.init();

const Experinces = ref([
  {
    id: 1,
    role: "Full Stack Developer",
    company: "Assyifa Islamic Philanthropy",
    information:
      "Project saat magang membuat Sistem Manajemen untuk mengatur seputar Zakat, Ziswaf dan Wakaf menggunakan Laravel.",
    date: "Desember 2022 - Januari 2023",
  },
  {
    id: 2,
    role: "Full Stack Developer",
    company: "Dinas Komunikasi dan Informatika",
    information:
      "Project saat magang membuat Sistem Informasi Manajemen Rumah Sakit (SIMRS) RS Harmoni Kehidupan dengan menggunakan Laravel + Vue JS + Bootstrap.",
    date: "Juli - September 2024",
  },
  {
    id: 3,
    role: "Full Stack Developer",
    company: "Project tugas kampus",
    information:
      "Membuat website sewa Photographer Pernikahan online (Go Photo) menggunakan PHP.",
    date: "Maret 2022 - September 2023",
  },
  {
    id: 4,
    role: "Full Stack Developer",
    company: "Project Tugas Akhir",
    information:
      "Project untuk menyelesaikan Tugas Akhir dengan membuat web showroom mobil bekas berbasis Chatbot untuk merekomendasikan mobil bekas menggunakan React JS + Laravel + Tailwind CSS + API Gemini (Menggunakan metode Analythical Hierarchy Process (AHP)).",
    date: "Tahun 2025",
  },
  {
    id: 5,
    role: "Full Stack Developer",
    company: "Klien",
    information:
      "Project membuat website untuk mengatur siswa Sekolah Dasar (SD) berbasis Chatbot untuk menampilkan data persiswa menggunakan Laravel + Bootstrap + API Gemini (Menggunakan metode C4.5).",
    date: "Tahun 2025",
  },
  {
    id: 6,
    role: "Full Stack Developer",
    company: "Klien",
    information:
      "Project membuat website untuk mengetahui tingkat kepuasan kepuasan pelanggan di toko Barnik Akbar berbasis Chatbot.",
    date: "Tahun 2025",
  },
]);
</script>
