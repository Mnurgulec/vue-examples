<template>
  <div class="container-box">
    <h2>Kullanıcı Bilgileri</h2>
    <input v-model="ad" placeholder="Adınızı giriniz" />
    <input v-model.number="yas" type="number" placeholder="Yaşınızı giriniz:" />
    
    <p>Merhaba {{ ad }}</p>
    <p>Yaşınız: {{ yas }}</p>
    
    <button @click="yasArtir">Yaşı 1 Arttır</button>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const ad = ref('');
const yas = ref(30);


const yasArtir = () => {
  yas.value++;
};
</script>



<style scoped>

input {
  display: block;
  margin: 5px 0;
  padding: 8px;
}
button {
  margin-top: 10px;
  padding: 8px 12px;
  cursor: pointer;
}
</style>
