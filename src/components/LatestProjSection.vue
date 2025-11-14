    <template>
        <section class="text-white mt-20" id="projects">
            <div class="px-4 xl:pl-16">
                <div class="mb-4 md:flex md:justify-between xl:pr-16">
                    <h2 class="text-4xl font-bold text-white"> My Latest Projects</h2>
                    <div class="flex space-x-4 mb-4 mt-5 md:mt-0">
                        <!-- <button class="hover:text-primary" v-for="category in ['all', 'web development', 'Mobile App']" -->
                        <button class="hover:text-primary" v-for="category in ['Full Stack Developer']"
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
                            <!-- <a class="h-14 w-14 mr-2 border-2 relative rounded-full border-[#ADB7BE] hover:border-white group/link"
                                :href="project.gitURL"> <svg xmlns="http://www.w3.org/2000/svg" fill="none"
                                    viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" aria-hidden="true"
                                    data-slot="icon"
                                    class="h-10 w-10 text-[#ADB7BE] absolute top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2  cursor-pointer group-hover/link:text-white">
                                    <path stroke-linecap="round" stroke-linejoin="round"
                                        d="M17.25 6.75 22.5 12l-5.25 5.25m-10.5 0L1.5 12l5.25-5.25m7.5-3-4.5 16.5">
                                    </path>
                                </svg></a> -->
                                <a class="h-14 w-14 border-2 relative rounded-full border-[#ADB7BE] hover:border-white group/link"
                                :href="project.webURL"> <svg xmlns="http://www.w3.org/2000/svg" fill="none"
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
                        <!-- <h3 class="text-lg font-semibold uppercase lg:text-xl"> {{ project.title }}</h3> -->
                        <h3 class="text-lg font-semibold lg:text-xl"> {{ project.title }}</h3>
                        <p class="text-[#ADB7BE]">{{ project.description }}</p>
                        <div class="flex flex-wrap p-2.5">
                            <div v-for="technology in project.technologies" :key="technology" class="text-center ml-1 mt-1 rounded-3xl bg-[#111827]"
                            style="box-shadow: 0 4px 30px rgba(0, 0, 0, 0.1); border: 1px solid #111827;backdrop-filter: blur(9px);-webkit-backdrop-filter: blur(9px);"
                            >
                        <p class="px-1 py-2">{{ technology }}</p>
                        </div>
                        </div>
                    </div>
                    </div>
                </ul>
            </div>
        </section>
    </template>
    <script setup>
    import { ref, computed } from 'vue';

    const Projects = ref([
        {
            id: 1,
            category: 'Full Stack Developer',
            image: '/project_1.png',
            title: 'Ass-Syifa Boarding School',
            description: 'Sebagai Full Stack Developer di salah satu pesantren modern yang ada di Tambakmekar, Kec. Jalancagak, Kab. Subang, Prov. Jawa Barat. Diamanahkan untuk mengelola / membuat salah satu website nya yang bernama Paguyuban untuk mengelola sistem keuangan dan data jumlah donatur di bagian Assyifa Islamic Philanthropy (AIP)',
            technologies: ['Laravel'],
            gitURL: '',
            webURL: '/project_1_full.png'
        },
        /*
        {
            id: 2,
            category: 'Mobile App',
            image: 'src/assets/mobile.jpg',
            title: 'project 1',
            description: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Hic tenetur quasi ipsam labore sapiente, accusamus necessitatibus laboriosam non voluptas inventore deserunt dolore modi ex, praesentium at provident nihil magni ratione!',
            technologies: ['vue.js 3', 'vuex', 'Express'],
            gitURL: '',
            webURL: ''
        },
        */
        {
            id: 3,
            category: 'Full Stack Developer',
            image: '/project_2.png',
            title: 'Go Photo',
            description: 'Sebagai Full Stack Developer di saat project tugas kampus secara berkelompok dengan di bagi beberapa kepengurusan yang pada akhirnya dinamakan Go Photo',
            technologies: ['PHP'],
            gitURL: '',
            webURL: '/project_2_full.png'
        },
        /*
        {
            id: 4,
            category: 'Mobile App',
            image: 'src/assets/mobile.jpg',
            title: 'project 1',
            description: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Hic tenetur quasi ipsam labore sapiente, accusamus necessitatibus laboriosam non voluptas inventore deserunt dolore modi ex, praesentium at provident nihil magni ratione!',
            technologies: ['vue.js 3', 'vuex', 'Express'],
            gitURL: '',
            webURL: ''
        },
        */
        {
            id: 5,
            category: 'Full Stack Developer',
            image: '/project_3.png',
            title: 'RS Harmoni Kehidupan',
            description: 'Di saat magang setelah menyelesaikan beberapa tugas yang diberikan untuk selanjutnya membuat project Sistem Informasi Manajemen Rumah Sakit (SIMRS) RS Harmoni Kehidupan',
            technologies: ['Laravel 11', 'Vue JS 3', 'Midtrans'],
            gitURL: '',
            webURL: '/project_3_full.png'
        },
        /*
        {
            id: 6,
            category: 'Mobile App',
            image: 'src/assets/mobile.jpg',
            title: 'project 1',
            description: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Hic tenetur quasi ipsam labore sapiente, accusamus necessitatibus laboriosam non voluptas inventore deserunt dolore modi ex, praesentium at provident nihil magni ratione!',
            technologies: ['vue.js 3', 'vuex', 'Express'],
            gitURL: '',
            webURL: ''
        }
        */
        {
            id: 7,
            category: 'Full Stack Developer',
            image: '/project_4.png',
            title: 'GM Mobilindo',
            description: 'Membuat project untuk menyelesaikan Tugas Akhir dengan membuat sistem berbasis Chatbot AI Gemini',
            technologies: ['Laravel 11', 'React JS', 'AI Gemini'],
            gitURL: '',
            webURL: '/project_4_full.png'
        },
        /*
        {
            id: 8,
            category: 'Mobile App',
            image: 'src/assets/mobile.jpg',
            title: 'project 1',
            description: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Hic tenetur quasi ipsam labore sapiente, accusamus necessitatibus laboriosam non voluptas inventore deserunt dolore modi ex, praesentium at provident nihil magni ratione!',
            technologies: ['vue.js 3', 'vuex', 'Express'],
            gitURL: '',
            webURL: ''
        }
        */
    ]);


    const selectedCategory = ref('all');
    const filteredProjects = computed(() => {
        if (selectedCategory.value === 'all') {
            return Projects.value;
        }
        return Projects.value.filter(project => project.category.toLocaleLowerCase() === selectedCategory.value.toLocaleLowerCase());
    })

    </script>
