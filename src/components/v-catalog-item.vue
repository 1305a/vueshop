<template>
  <div class="v-catalog-item">
      <img :src=" require('../assets/images/' + product_data.image) " alt="">
      <p class="v-catalog-item-name">{{product_data.name}}</p>
      <p class="v-catalog-item-price">{{product_data.price}}</p>
      <button class="v-catalog-item-cartbtn">Add to cart</button>
  </div>
</template>

<script>
export default {
    name: "v-catalog-item",
    props: {
        product_data: {
            type: Object,
            default() {
                return {}
            }
        }
    },
    data() {
        return {}
    },
    computed: {}
}
</script>

<style>
    .v-catalog-item {
        flex-basis: 25%;
        box-shadow: 0 0 8px 0 #e0e0e0;
        padding: 16px;
        margin-bottom: 16px;
    }
</style>