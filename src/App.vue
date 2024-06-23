<template>
  <div class="konten">
    <h1 class="animated-heading">Halaman Free Tugas</h1>
    <div class="container animated-background">
      <p>Selamat datang di Halaman Free Tugas!<br>
         Ini Merupakan Halaman Free tugas<br>
         yang mana bebas tugas pada tugas 2</p>
    </div>
    
    <div class="tugas-dropdown-container-sidebar"
         @mouseenter="showTugasDropdownSidebar"
         @mouseleave="hideTugasDropdownSidebar">

      <button class="tomboltugas" style="margin-top: 10px;" @click="toggleDropdown">
        Tugas 1 - 7
      </button>

      <div v-show="tugasDropdownSidebar" class="tugas-dropdown-list-horizontal">
        <div v-for="i in 7" :key="'tugas-sidebar-' + i"
             class="tugas-item"
             @click="goToTugas(i)">
          {{ `Tugas ${i}` }}
        </div>
      </div>

    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const tugasDropdownSidebar = ref(false);

const netlifyUrls = [
  'https://ahmad-projectcv.netlify.app',  
  'https://marifahmadn-223510434-lab-t2freetugas.netlify.app',  
  'https://marifahmad.netlify.app',  
  'https://marifahmad-223510434-prapbk.netlify.app',  
  'https://marifahmad-223510434-ppbk-t5-landingp.netlify.app',  
  'https://marifahmadnasution-223510434-t6-inapi.netlify.app',   
  'https://marifahmadnasution-223510434-t7-pinia.netlify.app'   
];

const showTugasDropdownSidebar = () => {
  tugasDropdownSidebar.value = true;
};

const hideTugasDropdownSidebar = () => {
  tugasDropdownSidebar.value = false;
};

const toggleDropdown = () => {
  tugasDropdownSidebar.value = !tugasDropdownSidebar.value;
};

const goToTugas = (tugasId) => {
  const url = netlifyUrls[tugasId - 1];
  window.location.href = url;
};

</script>

<style scoped>
.konten {
  margin-top: -50px;
  margin-left: 200px;
  background: transparent; 
  border: 2px solid rgba(255, 255, 255, 0.2);
  border-radius: 20px;
  backdrop-filter: blur(20px);
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
  padding: 20px;
  width: 850px;
  text-align: center;
  color: #fff;
}

.animated-heading {
  font-family: 'Roboto', sans-serif;
  font-size: 2.5rem;
  margin-bottom: 20px;
  animation: rainbowText 5s infinite;
}

@keyframes rainbowText {
  0% { color: #ff0000; } 
  20% { color: #ff8000; } 
  40% { color: #ffff00; } 
  60% { color: #00ff00; } 
  80% { color: #0000ff; } 
  100% { color: #800080; } 
}

.animated-background {
  padding: 10px;
  font-family: 'Arial', sans-serif;
  font-size: 1.2rem;
  line-height: 1.6;
  background-color: #f9f9f9; 
  animation: rainbowBackground 10s infinite; 
}

@keyframes rainbowBackground {
  0% { background-color: #f9f9f9; } 
  20% { background-color: #ffd700; } 
  40% { background-color: #ff69b4; } 
  60% { background-color: #00ced1; } 
  80% { background-color: #90ee90; } 
  100% { background-color: #dda0dd; } 
}

p {
  color: #fff;
}

.tomboltugas {
  cursor: pointer;
  padding: 10px 20px;
  background-color: #4CAF50; 
  color: white;
  border: none;
  border-radius: 5px;
  font-size: 1rem;
  transition: background-color 0.3s ease;
}

.tomboltugas:hover {
  background-color: #45a049; /* Warna latar belakang saat dihover */
}

/* Gaya untuk daftar dropdown tugas */
.tugas-dropdown-list-horizontal {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  margin-top: 10px; /* Adjust spacing from button */
}

/* Gaya untuk item tugas dalam dropdown */
.tugas-item {
  cursor: pointer;
  padding: 10px;
  color: #fff;
  transition: background-color 0.3s ease;
  flex: 1 0 auto; /* Ensure items take equal space */
  max-width: calc(100% / 7 - 20px); /* Adjust width based on number of items */
  margin: 5px; /* Add margin between items */
  animation-duration: 10s; /* Durasi animasi 10 detik */
  animation-iteration-count: infinite; /* Animasi tak terbatas */
}

/* Animasi latar belakang untuk setiap item tugas */
.tugas-item:nth-child(1) {
  animation-name: rainbowBackground-1;
}
.tugas-item:nth-child(2) {
  animation-name: rainbowBackground-2;
}
.tugas-item:nth-child(3) {
  animation-name: rainbowBackground-3;
}
.tugas-item:nth-child(4) {
  animation-name: rainbowBackground-4;
}
.tugas-item:nth-child(5) {
  animation-name: rainbowBackground-5;
}
.tugas-item:nth-child(6) {
  animation-name: rainbowBackground-6;
}
.tugas-item:nth-child(7) {
  animation-name: rainbowBackground-7;
}

.tugas-item:hover {
  background-color: rgba(255, 255, 255, 0.1);
}
@keyframes rainbowBackground-1 {
  0% { background-color: #f9f9f9; } 
  20% { background-color: #ffd700; } 
  40% { background-color: #ff69b4; } 
  60% { background-color: #00ced1; } 
  80% { background-color: #90ee90; } 
  100% { background-color: #dda0dd; } 
}

@keyframes rainbowBackground-2 {
  0% { background-color: #f9f9f9; } 
  20% { background-color: #ff6347; }
  40% { background-color: #7b68ee; }
  60% { background-color: #3cb371; } 
  80% { background-color: #9370db; }
  100% { background-color: #ffa500; } 
}

@keyframes rainbowBackground-3 {
  0% { background-color: #f9f9f9; } 
  20% { background-color: #ff1493; } 
  40% { background-color: #1e90ff; } 
  60% { background-color: #ffc0cb; } 
  80% { background-color: #4682b4; } 
  100% { background-color: #dda0dd; } 
}

@keyframes rainbowBackground-4 {
  0% { background-color: #f9f9f9; } 
  20% { background-color: #ffff00; } 
  40% { background-color: #00ff00; } 
  60% { background-color: #ff00ff; } 
  80% { background-color: #00ffff; } 
  100% { background-color: #ff4500; } 
}

@keyframes rainbowBackground-5 {
  0% { background-color: #f9f9f9; } 
  20% { background-color: #ff00ff; } 
  40% { background-color: #32cd32; } 
  60% { background-color: #ffff00; } 
  80% { background-color: #00ffff; } 
  100% { background-color: #ff4500; } 
}

@keyframes rainbowBackground-6 {
  0% { background-color: #f9f9f9; } 
  20% { background-color: #ff6347; } 
  40% { background-color: #7b68ee; } 
  60% { background-color: #3cb371; } 
  80% { background-color: #9370db; } 
  100% { background-color: #ffa500; } 
}

@keyframes rainbowBackground-7 {
  0% { background-color: #f9f9f9; } 
  20% { background-color: #ffa500; } 
  40% { background-color: #90ee90; } 
  60% { background-color: #dda0dd; } 
  80% { background-color: #ff6347; } 
  100% { background-color: #7b68ee; } 
}


</style>
<style>
body {
  height: 100vh;
  color: #fff;
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 100vh;
  background: url('/src/assets/image/JEPANGMALAM.jpg') no-repeat;
  background-size: cover;
  background-position: center;
  margin: 0; 
  padding: 0; 
}</style>
