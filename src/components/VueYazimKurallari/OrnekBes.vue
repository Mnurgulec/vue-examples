<template>
  <div class="container-box">
    <h2>v-for ile Yemek Fiyat Listesi</h2>
    <ul>
      <li v-for="yemek in yemekFiltrele" :key="yemek.id">
        {{ yemek.isim }} - {{ yemek.fiyat }} TL
      </li>
    </ul>
  </div>
</template>


<script>
export default {
  data() {
    return {
      yemekler: [
        { id: 1, isim: "Hamburger", fiyat: 75 },
        { id: 2, isim: "Pizza", fiyat: 80 },
        { id: 3, isim: "Salata", fiyat: 45 },
        { id: 4, isim: "Tost", fiyat: 30 },
        { id: 5, isim: "Makarna", fiyat: 60 }
      ]
    };
  },

  computed: {
    yemekFiltrele() {

      return this.yemekler.filter(yemek => yemek.fiyat <= 1000);
    }
  }
};
</script>
