<template>
  <div class="v-catalog-item">
      <img class="v-catalog-item-image" :src=" require('../assets/images/' + product_data.image) " alt="">
      <p class="v-catalog-item-name">{{product_data.name}}</p>
      <p class="v-catalog-item-price">{{product_data.price}} р.</p>
      <button 
      class="v-catalog-item-cartbtn" 
      @click="addToCart"
      >Add to cart</button>
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
    computed: {},
    methods: {
        addToCart() {
            this.$emit('addToCart',this.product_data)
        }
    },
    mounted() {
        this.$set(this.product_data, 'quantity', 1) //fix by comments
    }
}
</script>

<style>
    .v-catalog-item {
        flex-basis: 25%;
        box-shadow: 0 0 8px 0 #e0e0e0;
        padding: 16px;
        margin-bottom: 16px;
    }
    .v-catalog-item-image {
        width: 100px;
    }
    .v-catalog-item-cartbtn {
        padding: 8px 16px;
        background: rgb(28, 175, 84);
        color: white;
        border: 0;
        border-radius: 4px;
    }
</style>