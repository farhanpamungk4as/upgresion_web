<script setup>
import logo from '../../assets/LOGO.png';
import { ref, onMounted } from 'vue';

const isOpen = ref(false);

const navigation = [
  { name: 'About Usp', href: '#' },
  { name: 'Program', href: '#' },
  { name: 'Internship', href: '#' },
  { name: 'Article', href: '#' },
  { name: 'Contact Us', href: '#' },
  { name: 'Donate', href: '#' },
  { name: 'UpgreTech', href: '#' },
];

onMounted(() => {
  document.documentElement.style.overflowX = "hidden";
  document.body.style.overflowX = "hidden";
});
</script>

<template>
  <nav class="w-full bg-white fixed top-0 left-0 right-0 shadow-md z-50">
    <div class="max-w-screen-xl mx-auto flex items-center justify-between px-6 lg:px-12 py-3">
      <!-- Logo -->
      <div class="p-2 lg:-ml-15">
        <img class="h-12" :src="logo" alt="Logo">
      </div>

      <!-- Hamburger Button (SM) -->
      <button @click="isOpen = !isOpen" class="lg:hidden p-2 focus:outline-none">
        <svg class="w-8 h-8 text-gray-700" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16m-7 6h7"></path>
        </svg>
      </button>

      <!-- Menu Navigasi (LG) -->
      <div class="hidden lg:flex lg:gap-x-10 lg:justify-center lg:w-full lg:-ml-45">
        <a v-for="item in navigation" :key="item.name" :href="item.href"
          class="text-gray-700 hover:text-blue-500 font-medium text-md">
          {{ item.name }}
        </a>
      </div>
    </div>

    <!-- Menu Navigasi (SM) -->
    <div v-if="isOpen" class="absolute top-14 left-0 w-full bg-white shadow-md">
      <div class="flex flex-col items-center py-4 space-y-4">
        <a v-for="item in navigation" :key="item.name" :href="item.href"
          class="text-gray-700 hover:text-blue-500 font-medium text-md">
          {{ item.name }}
        </a>
      </div>
    </div>
  </nav>
</template>
