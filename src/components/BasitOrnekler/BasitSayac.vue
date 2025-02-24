<template>
  <div class="container-box">
    <p>{{ sayac }}</p>
    <button @click="arttır">Arttır</button>
    <p> Composition API ile yazılmış basit bir sayaç</p>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const sayac = ref(99);

const arttır = () => {
  sayac.value++;
};
</script>
