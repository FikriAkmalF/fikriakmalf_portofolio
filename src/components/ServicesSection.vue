<template>
  <section class="text-white mt-20" id="services">
    <div class="px-4 xl:pl-16">
      <h2 class="text-4xl font-bold text-white mb-4">My Skills</h2>
    </div>

    <div class="flex flex-wrap gap-4 px-4 xl:pl-16 mt-10">
      <button
        v-for="category in categories"
        :key="category"
        @click="activeCategory = category"
        class="px-6 py-3 rounded-xl border transition-all duration-300 text-sm md:text-base font-semibold"
        :class="[
          // Cek jika kategori ini aktif
          activeCategory === category
            ? 'text-white border-transparent bg-gradient-to-r from-primary to-pink-500' // Warna aktif sesuai contoh gambar
            : 'text-white border-white bg-[#111a3e] hover:border-primary', // Warna non-aktif sesuai background card
        ]"
      >
        {{ category }}
      </button>
    </div>
    <div
      class="py-8 xl:px-16 px-4 sm:py-16 grid grid-cols-1 gap-6 pt-10 sm:grid-cols-2 md:gap-10 md:pt-12 lg:grid-cols-3"
    >
      <div
        v-for="service in filteredServices"
        :key="service.id"
        data-aos="fade-up"
        class="px-8 py-12 rounded-xl bg-[#111a3e] shadow-lg border border-[#1f1641]"
      >
        <div class="mx-auto h-24 w-24 text-center xl:h-24 xl:w-24">
          <div>
            <img :src="service.icon" :alt="service.name + ' icon'" />
          </div>
        </div>
        <div class="text-center">
          <h3
            class="pt-5 text-lg font-semibold text-transparent bg-clip-text bg-gradient-to-r from-primary to-secondary lg:text-xl"
          >
            {{ service.name }}
          </h3>
          <!-- <p
            class="text-grey pt-4 text-sm text-justify xgroup-hover:text-white md:text-base"
          >
            {{ service.description }}
          </p> -->
        </div>
      </div>

      <div v-if="filteredServices.length === 0" class="lg:col-span-3 text-center py-10">
        <p class="text-gray-400">
          Tidak ada keterampilan yang tersedia dalam kategori **{{ activeCategory }}**
          saat ini.
        </p>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref, computed } from "vue";
import AOS from "aos";
import "aos/dist/aos.css";

AOS.init();

// 1. Data Kategori
const categories = ref([
  "All",
  "Frontend",
  "Backend",
  "DevOps",
  "Databases",
  "Tools",
  "Soft Skills",
]);
const activeCategory = ref("All"); // Kategori default yang aktif

// 2. Data Keterampilan (Tambahkan properti 'category')
const services = ref([
  {
    id: 1,
    icon: "https://img.icons8.com/?size=100&id=NfbyHexzVEDk&format=png&color=000000",
    name: "React JS",
    description:
      "Framework JavaScript yang digunakan untuk membangun antarmuka pengguna (UI) yang interaktif dan efisien, terutama dalam aplikasi berbasis Single Page Application (SPA).",
    category: "Frontend",
  },
  {
    id: 2,
    icon: "https://img.icons8.com/?size=100&id=fdBWYEwusJbm&format=png&color=ffffff",
    name: "React Query",
    description:
      "React Query adalah sebuah library manajemen state yang bertujuan tunggal: membuat fetching, caching, dan sinkronisasi data dari server (API) di aplikasi React menjadi otomatis dan mudah.",
    category: "Frontend",
  },
  {
    id: 3,
    icon: "https://img.icons8.com/?size=100&id=4PiNHtUJVbLs&format=png&color=000000",
    name: "Tailwind CSS",
    description:
      "Framework JavaScript progresif untuk membangun antarmuka pengguna, dikenal karena sintaksisnya yang mudah dipelajari dan performa yang baik.",
    category: "Frontend",
  },
  {
    id: 4,
    icon: "https://img.icons8.com/?size=100&id=PndQWK6M1Hjo&format=png&color=000000",
    name: "Bootstrap",
    description:
      "Framework CSS yang digunakan untuk membangun antarmuka web yang responsif dan cepat dengan komponen siap pakai. Biasa nya saat project digunakan untuk Laravel",
    category: "Frontend",
  },
  {
    id: 5,
    icon: "https://img.icons8.com/?size=100&id=gFw7X5Tbl3ss&format=png&color=000000",
    name: "Material-UI",
    description: "",
    category: "Frontend",
  },
  {
    id: 1,
    icon: "https://img.icons8.com/?size=100&id=hUvxmdu7Rloj&format=png&color=000000",
    name: "Laravel",
    description:
      "Framework PHP yang digunakan untuk membangun aplikasi web dengan struktur yang rapi, aman, dan efisien. Bisa digabungkan dengan Vue JS / React JS jika digabung maka Laravel digunakan sebagai Backend",
    category: "Backend",
  },
  {
    id: 2,
    icon: "https://img.icons8.com/?size=100&id=21888&format=png&color=ffffff",
    name: "REST API",
    description:
      "REST API singkatan dari Representational State Transfer Application Programming Interface. REST API adalah set aturan arsitektur yang memungkinkan dua sistem yang berbeda untuk berkomunikasi dan bertukar data melalui internet, menggunakan protokol standar HTTP.",
    category: "Backend",
  },
  {
    id: 3,
    icon: "https://img.icons8.com/?size=100&id=54087&format=png&color=000000",
    name: "Node JS",
    description: "",
    category: "Backend",
  },
  {
    id: 4,
    icon: "https://upload.wikimedia.org/wikipedia/commons/2/27/PHP-logo.svg",
    name: "PHP",
    description: "",
    category: "Backend",
  },
  {
    id: 1,
    icon: "https://img.icons8.com/?size=100&id=LdUzF8b5sz2R&format=png&color=000000",
    name: "Docker",
    description: "",
    category: "DevOps",
  },
  {
    id: 1,
    icon: "https://img.icons8.com/?size=100&id=QeIg9siFKGgp&format=png&color=000000",
    name: "MySQL",
    description: "",
    category: "Databases",
  },
  // {
  //   id: 2,
  //   icon: "https://img.icons8.com/?size=100&id=JRnxU7ZWP4mi&format=png&color=000000",
  //   name: "PostgreSQL",
  //   description:
  //     "",
  //   category: "Databases",
  // },
  {
    id: 1,
    icon: "https://img.icons8.com/?size=100&id=20906&format=png&color=000000",
    name: "Git",
    description: "",
    category: "Tools",
  },
  {
    id: 2,
    icon: "https://img.icons8.com/?size=100&id=3tC9EQumUAuq&format=png&color=ffffff",
    name: "GitHub",
    description: "",
    category: "Tools",
  },
  {
    id: 1,
    icon: "https://img.icons8.com/?size=100&id=1609&format=png&color=ffffff",
    name: "Bekerja sama",
    description:
      "Bekerja sama adalah suatu kegiatan atau proses di mana dua orang atau lebih (individu, tim, atau organisasi) berinteraksi dan berkolaborasi untuk mencapai satu tujuan bersama yang telah ditetapkan.",
    category: "Soft Skills",
  },
  {
    id: 2,
    icon: "https://img.icons8.com/?size=100&id=54385&format=png&color=ffffff",
    name: "Komunikasi",
    description:
      "Komunikasi adalah aksi pertukaran informasi atau interaksi dua arah yang melibatkan pengiriman pesan (berbicara, menulis, atau gestur) dan penerimaan pesan (mendengarkan atau membaca) antara satu individu dengan individu atau kelompok lain. Intinya adalah interaksi yang efektif yang bertujuan untuk menciptakan pemahaman yang sama (mutual understanding) mengenai suatu topik, ide, atau arahan, baik secara internal dalam tim maupun secara eksternal dengan klien atau pengguna.",
    category: "Soft Skills",
  },
]);

// 3. Fungsi Filtering menggunakan computed property
const filteredServices = computed(() => {
  if (activeCategory.value === "All") {
    return services.value;
  }
  return services.value.filter((service) => service.category === activeCategory.value);
});
</script>
