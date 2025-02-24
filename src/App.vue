<template>
  <div>
    <MyComponent />
    <BasitSayac /> 
    <OrnekBir />
    <vbindOrnek/>
    <vifOrnek/>
        <vshow/>
           <vfor/>
            <hesapmakinesi/>
                        <OrnekAlti/>
                        <vmodel/>
  <div class="container-box">

   <h3>vue Emit ile iletişim</h3>
    <GonderenComponent @mesajGonderildi="mesajAl" />
    <AlanComponent :mesaj="mesaj" />
</div>
  </div>
</template>

<script setup>
import MyComponent from './components/HelloWorld.vue';
import BasitSayac from './components/BasitOrnekler/BasitSayac.vue';
import OrnekBir from './components/VueYazimKurallari/OrnekBir.vue';
import vbindOrnek from './components/VueYazimKurallari/OrnekIki.vue';
import vifOrnek from './components/VueYazimKurallari/OrnekUc.vue';
import vshow from './components/VueYazimKurallari/OrnekDort.vue';
import vfor from './components/VueYazimKurallari/OrnekBes.vue';
import hesapmakinesi from './components/HesapMakinesi/HesapMakinesi.vue';
import OrnekAlti from './components/VueYazimKurallari/OrnekAlti.vue';
import vmodel from './components/VueYazimKurallari/OrnekYedi.vue';


import { ref } from "vue";
import GonderenComponent from "./components/VueYazimKurallari/GonderenComponent.vue";
import AlanComponent from "./components/VueYazimKurallari/AlanComponent.vue";

const mesaj = ref("");

const mesajAl = (gelenMesaj) => {
  mesaj.value = gelenMesaj;
};

</script>

