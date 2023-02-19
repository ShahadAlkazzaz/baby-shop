<script setup>
import HeroImage from "../components/HeroImage.vue";
import ClothesOffers from "../components/ClothesOffers.vue";
import FooterSide from "../components/FooterSide.vue";
</script>

<template>
  <HeroImage />

  <h1 class="kataloge">{{ message }}</h1>

  <div class="all-kataloge">
    <div  class="container text-center">
      <div id="clothes-container" class="row align-items-start">
        <clothe-offers
          v-for="clothe in clothes"
          :key="clothe.id"
          :sale="clothe"
          :img="image"
        />
        <input  type="button" class="btn btn-primary" :value="value">
        <!-- <ClothesOffers /> -->
      </div>
    </div>

    <p>
        {{ value }}
      </p>
  </div>
  <FooterSide />
</template>

<script>
export default {
  data() {
    return {
      message: "Kataloge",
      clothes: [],
      value:0,
    };
  },

  components: { "clothe-offers": ClothesOffers },
  mounted() {
    this.fetchData();
  },
  methods: {
    async fetchData() {
      const res = await fetch("baby.json");
      const result = await res.json();
      this.clothes = result;
    },
    increase() {
        this.value = this.value +1
      },

  },

};
</script>

<style scoped>
.all-kataloge {
  margin-top: 15vh;
  /* gap: 15px; */

}
/* #clothes-container{

} */
.kataloge,
h1 {
  display: flex;
  justify-content: center;
  margin-top: 5vh;
  margin-bottom: 30px;
}
</style>
