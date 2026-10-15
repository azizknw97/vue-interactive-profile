
<script setup>
import { ref } from 'vue'

// Menyimpan skor pemain
const skor = ref(0)

// Menyimpan pesan permainan
const pesan = ref('Klik target untuk mendapatkan skor!')

// Aksi saat target diklik
function klikTarget() {
  skor.value++
  pesan.value = 'Mantap! Kamu mendapatkan 1 poin!'
}

// Mengulang permainan
function ulangiGame() {
  skor.value = 0
  pesan.value = 'Klik target untuk mendapatkan skor!'
  
}
</script>

<template>
  <main class="game-container">
    <section class="game-card">
      <p class="label">MINI GAME VUE.JS</p>

      <h1>🎯 Tangkap Klik!</h1>

      <p class="description">
        Klik target sebanyak mungkin dan kumpulkan poin!
      </p>

      <div class="score-box">
        <span>SKOR KAMU</span>
        <strong>{{ skor }}</strong>
      </div>

      <button class="target" @click="klikTarget">
        🎯 KLIK AKU!
      </button>

      <p class="message">{{ pesan }}</p>

      <button class="reset" @click="ulangiGame">
        🔄 Ulangi Game
      </button>

      <p v-if="skor >= 10" class="winner">
        🏆 Hebat! Kamu sudah mendapatkan 10 poin!
      </p>
    </section>
  </main>
</template>
