<template>
<div>
<h2>Ürün Stok Durumu(v-if kullanımı)</h2>
<p v-if="stok >5"> Ürün stoıkta var>
<p v-else-if="stok>0 >Stokta birkaç ürün kaldı>
<p v-else> Ürün tükendi</p>
<button @click="stokArtir">Stok Arttır</button>
<button @click="stokAzalt">Stok Azalt</button>
<p>Mevcut stok: {{ stok }}</p>
</div>

</template>

<script>
import  { ref } from "vue";

export default {
    setup(){
        const stok= ref(3);

        const stokArtir = () => {
            sto.value++;
        };

        const stokAzalt = () => {
            if(stok.value>0){
            stok.value--;
            }
        };

        return{
            stok,
            stokArtir,
            stokAzalt
        };
    }
};
</script>