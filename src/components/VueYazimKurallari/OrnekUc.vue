<template>
  <div class="container-box">
    <h2>Ürün Stok Durumu (v-if kullanımı)</h2>

    <p v-if="stok > 5">   Ürün stokta var</p>
    <p v-else-if="stok > 0"> Stokta birkaç ürün kaldı</p>
    <p v-else>Ürün tükendi</p>

    <button @click="stokArtir">Stok Arttır</button>
    <button @click="stokAzalt">Stok Azalt</button>
    
    <p>Mevcut stok: {{ stok }}</p>
  </div>
</template>

<script>
import { ref } from "vue";

export default {
  setup() {
    const stok = ref(3); 
 

    const stokArtir = () => {
      stok.value++;
    };

    const stokAzalt = () => {
      if (stok.value > 0) {
        stok.value--;
      }
    };

    return {
      stok,
      stokArtir,
      stokAzalt
    };
  }
};
</script>


<style scoped>
button {

  margin: 5px;
  padding: 8px 12px;
  border: none;
  background-color: #3498db;
  color: white;
  cursor: pointer;
  border-radius: 5px;
}

button:hover {
  background-color: #2980b9;
}
</style>
