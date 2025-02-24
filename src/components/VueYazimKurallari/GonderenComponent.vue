<template>
  <div>
    <button @click="gonder">Mesajı gönder</button>
  </div>
</template>




<script setup>
import { defineEmits } from "vue";


const emit = defineEmits(["mesajGonderildi"]);


const gonder = () => {
  emit("mesajGonderildi", " GonderenComponent'ten mesaj geldi");
};
</script>
