<template>
  <div
    style="overflow: auto; width: 30%; border-radius: 6px"
    class="bg-green-1 shadow-10"
  >
    <div
      style="
        width: 200px;
        height: 200px;
        margin-left: auto;
        margin-right: auto;
        margin-top: 10px;
      "
    >
      <q-img
        :src="produit?.image"
        spinner-color="primary"
        spinner-size="82px"
        style="width: 200px; height: 200px; background-color: transparent"
        class="q-ml-auto q-mr-auto"
      />
    </div>
    <div
      class="text-center text-bold text-green q-ml-auto q-mt-lg"
      style="font-size: 170%; text-transform: capitalize"
    >
      {{ produit?.prix }}
    </div>
    <div
      class="text-center text-bold text-white bg-blue-4 q-ml-auto q-mr-auto q-mt-sm"
      style="font-size: 170%; text-transform: capitalize; width: 80%"
    >
      {{ produit?.designation }}
    </div>
    <div class="flex items-center justify-center">
      <div class="">
        <q-btn
          name="favorite"
          icon="favorite"
          color="red-6"
          style="margin-right: 0px"
          flat
        /><span style="margin-left: 0px; color: red">{{ produit?.favs }}</span>
        <q-btn
          name="thumb_up"
          icon="thumb_up"
          color="blue-4"
          style="margin-right: 0px"
          flat
        /><span style="margin-left: 0px" class="text-blue-4">{{
          produit?.like
        }}</span>
      </div>
    </div>
  </div>
</template>

<script setup>
const props = defineProps({
  produit: {
    type: Object,
  },
});
</script>

<style lang="scss" scoped></style>
