<template>
  <div class="container-box">
    <h1>Hesap Makinesi</h1>
    <div id="hesap-makinesi">
      <div class="ust">
        <button @click="ekran = ''">Temizle</button><br><br>
        <div class="ekran">{{ ekran || "0" }}</div>
      </div>
      <div class="tuslar">
        <span v-for="tus in tuslar" :key="tus" @click="tusaTikla(tus)" :class="{ operator: isOperator(tus), esittir: tus === '=', temizle: tus === 'C' }">
          {{ tus }}
        </span>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";

const ekran = ref("");
const tuslar = ["7", "8", "9", "+", "4", "5", "6", "-", "1", "2", "3", "÷", "0", ".", "=", "x"];

const operatorler = ["+", "-", "x", "÷"];

const tusaTikla = (tus) => {
  if (tus === "=") {
    try {
      ekran.value = eval(ekran.value.replace(/x/g, "*").replace(/÷/g, "/")) || "0";
    } catch {
      ekran.value = "Hata!";
    }
  } else {
    ekran.value += tus;
  }
};

const isOperator = (tus) => operatorler.includes(tus);
</script>

<style scoped>
* { margin: 0; padding: 0; box-sizing: border-box; font: bold 14px Arial, sans-serif; }
html { height: 100%; background: radial-gradient(circle, #fff 20%, #ccc); background-size: cover; }
#hesap-makinesi { width: 325px; margin: 10px auto; padding: 20px; background: linear-gradient(#9dd2ea, #8bceec); border-radius: 5px; box-shadow: 0px 4px #009de4, 0px 10px 15px rgba(0, 0, 0, 0.2); }
.ust .ekran { height: 40px; width: 100%; background: rgba(0, 0, 0, 0.2); border-radius: 5px; font-size: 20px; line-height: 40px; color: white; text-align: right; padding: 0 10px; }
.tuslar { display: grid; grid-template-columns: repeat(4, 1fr); gap: 10px; margin-top: 10px; }
.tuslar span { display: flex; align-items: center; justify-content: center; width: 100%; height: 50px; background: white; border-radius: 5px; cursor: pointer; font-size: 18px; transition: 0.2s; }
.tuslar span.operator { background: #ffcccc; }
.tuslar span.esittir { background: #f1ff92; }
button { margin: 5px; padding: 8px 12px; border: none; background-color: #3498db; color: white; cursor: pointer; border-radius: 5px; }
</style>
