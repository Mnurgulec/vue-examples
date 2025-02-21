<template>
  <div class="container-box">
    <h3>v-bind Örneği</h3>

    <img :src="resimurl" alt="logo" width="150" />

    <button :style="{ backgroundColor: butonrenk }" @click="renkDegistir">
      Renk Değiştir
    </button>
  </div>
</template>

<script setup>
import { ref } from 'vue';

import logo from '@/assets/logo.png';

const resimurl = ref(logo);
const butonrenk = ref('blue');

const renkDegistir = () => {
  butonrenk.value = butonrenk.value === 'blue' ? 'pink' : 'blue';
};
</script>

<style scoped>


button {
  color: white;
  padding: 8px 12px;
  border: none;
  cursor: pointer;
  margin-top: 10px;
}
</style>
