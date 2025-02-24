<template>
  <div class="container-box" :class="{ 'dark-mode': darkMode }">
    <h2>Ref kullanımı </h2>

    <div>
      <input type="text" v-model="isim" placeholder="Adınızı girin">
      <p>Karakter Sayısı: {{ isim.length }}</p>
    </div>

    <hr>

    <div>
      <p>Rastgele Sayı: {{ rastgeleSayi }}</p>
      <button @click="rastgeleSayi = Math.floor(Math.random() * 100) + 1">Sayı üret</button>
    </div>

    <hr>

 

    <div>
      <p>Geri Sayım: {{ geriSayim }}</p>
      <button @click="geriSayimiBaslat">Başlat</button>
    </div>

    <hr>

    <div>
      <button @click="darkMode = !darkMode">Tema değiştir</button>
      <p>Şu an: {{ darkMode ? "Koyu Mod" : "Açık Mod" }}</p>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";

const isim = ref("");

const rastgeleSayi = ref(0);




const geriSayim = ref(10);
const geriSayimiBaslat = () => {
  let interval = setInterval(() => {
    if (geriSayim.value > 0) {
      geriSayim.value--;
    } else {
      clearInterval(interval);
    }
  }, 1000);
};

const darkMode = ref(false);
</script>

<style scoped>
.container-box {
  padding: 20px;
  transition: background 0.3s, color 0.3s;
}
button {
  margin: 5px;
  padding: 8px 12px;
  border: none;
  background-color:rgb(230, 183, 232);
  color: white;
  cursor: pointer;
  border-radius: 5px;
}
button:hover {
  background-color:rgb(158, 46, 89);
}

.buttons {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 5px;
}

.dark-mode {
  background: #333;
  color: white;
}
</style>
