<template>
  <div>
    <h3>Alan component</h3>
    <p v-if="mesaj">{{ mesaj }}</p>
  </div>
</template>

<script setup>
import { defineProps } from "vue";

defineProps({
  mesaj: String,
});
</script>
