<script setup>
import ellipse1 from '../../assets/Ellipse 7.png';
import ellipse2 from '../../assets/Ellipse 4.png';
import ellipse3 from '../../assets/Ellipse 6.png';

const images = [
  { src: ellipse1, alt: 'Gambar 1' },    
  { src: ellipse2, alt: 'Gambar 2' },
  { src: ellipse3, alt: 'Gambar 3' }
];
</script>

<template>
  <!-- ✅ Tampilan Desktop (LG) -->
  <div class="relative hidden lg:flex justify-center items-center p-4 -mt-30">
    <!-- Gambar ke-3 (tengah atas) -->
    <div class="absolute top-[-17px] lg:w-67 lg:h-60"> 
      <img :src="images[2].src" :alt="images[2].alt" class="w-full h-full object-contain">
    </div>

    <!-- Wrapper untuk dua gambar lainnya -->
    <div class="flex gap-20 mt-10">
      <div v-for="(image, index) in images.slice(0, 2)" :key="index" class="relative lg:w-60 lg:h-60 top-[-18px]">
        <img :src="image.src" :alt="image.alt" class="w-full h-full object-contain">
      </div>
    </div>
  </div>

  <!-- ✅ Tampilan Mobile & Tablet (SM, MD) -->
  <div class="relative flex lg:hidden flex-col items-center p-4 -mt-40">
    <!-- Gambar ke-3 (di tengah atas) -->
    <div class="absolute top-[10px] w-47 h-31"> 
      <img :src="images[2].src" :alt="images[2].alt" class="w-full h-full object-contain">
    </div>

    <!-- Wrapper untuk dua gambar lainnya -->
    <div class="flex gap-20 mt-10">
      <div v-for="(image, index) in images.slice(0, 2)" :key="index" class="relative w-35 h-35 top-[-18px]">
        <img :src="image.src" :alt="image.alt" class="w-full h-full object-contain">
      </div>
    </div>
  </div>
</template>
