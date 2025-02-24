<template>
  <div class="container-box">
<button @click="gorunurYap= !gorunurYap">
{{ gorunurYap ? 'Gizle' : 'Göster'}}
</button>

<div v-show="gorunurYap"> v-show ile içerik gözüküyor.<br>  V-show, elementi DOMda tutarak sadece display : none ile gizler.<br> V-if ise elementi tamamen DOM dan kaldırıp tekrar ekler </div></div>
</template>

<script>
export default {
  data() {
    return {
      gorunurYap: true 
    };
  }
};
</script>
