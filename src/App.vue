<template>
  <div>
    <h1>Vue Playground</h1>
    <MyComponent />
    <BasitSayac /> 
    <OrnekBir />
    <vbindOrnek/>
    <vifOrnek/>

  </div>
</template>

<script setup>
import MyComponent from './components/HelloWorld.vue';
import BasitSayac from './components/BasitOrnekler/BasitSayac.vue';
import OrnekBir from './components/VueYazimKurallari/OrnekBir.vue';
import vbindOrnek from './components/VueYazimKurallari/OrnekIki.vue';
import vifOrnek from './components/VueYazimKurallari/vifOrnek.vue';



</script>

