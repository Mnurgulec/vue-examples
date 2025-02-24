<template>
   <div class="container-box">  
    <p>Fareyi kutunun üzerine getirdiğinde event ile konum gösterme:</p>
    <div @mousemove="hareketTakip">
      X: {{ x }}, Y: {{ y }}
    </div>
  </div>


</template>

<script>
import { ref } from "vue";

export default {
  setup() {
    const x = ref(0);
    const y = ref(0);

    const hareketTakip = (event) => 
    {
      x.value = event.clientX;
      y.value = event.clientY;
    
    
    };

    return { x, y, hareketTakip };
  }
};
</script>
