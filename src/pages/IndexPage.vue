<template>
  <div class="q-gutter-lg q-pa-sm row">
    <!-- v-on. Elle est utilisée pour écouter des événements émis par un composant enfant. -->
    <ProductComponent
      :produit="item"
      v-for="(item, index) in produits"
      :key="index"
      @updateLike="(id) => updateLike(id)"
      @updateFav="(id) => updateFav(id)"
      @commenter="(obj) => commenter(obj)"
    />
  </div>

  <!-- Ici je vais placer le header -->
</template>

<script setup>
import ProductComponent from "src/components/ProductComponent.vue";
import { ref } from "vue";
const produits = ref([
  {
    id: 1,
    image: "https://www.youtube.com/embed/lGyWMsXel2U",

    favs: 220,
    like: 200,
    comments: ["Ok"],
  },

  {
    id: 4,
    image: "https://www.youtube.com/embed/lGyWMsXel2U",

    favs: 2200,
    like: 2400,
    comments: ["Belle video"],
  },
]);
const updateLike = (id) => {
  produits.value.find((el) => el.id === id).like++;
};
const updateFav = (id) => {
  produits.value.find((el) => el.id === id).favs++;
};
const commenter = (obj) => {
  produits.value.find((el) => el.id === obj.id).comments.push(obj.comment);
};
</script>

<style>
.log {
  font-weight: bolder;
}
</style>
