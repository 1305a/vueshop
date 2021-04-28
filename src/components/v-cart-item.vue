<template>
  <div class='v-cart-item'>
    <img class="v-cart-item-image" :src=" require('../assets/images/' + cart_item_data.image) " alt="">
    <div class="v-cart-item-info">
        <p>{{cart_item_data.name}} </p>
        <p>{{cart_item_data.price}}</p>
        <p>{{cart_item_data.article}}</p>
    </div>
    <div class="v-cart-item-quantity">
        <p>Qty</p>
        <span class="quantity-btn" @click="decrementItem">-</span>
        {{cart_item_data.quantity}}
        <span class="quantity-btn" @click="incrementItem">+</span>
    </div>
    <button @click="deleteFromCart">Delete</button>
  </div>
</template>

<script>
// import {mapActions} from 'vuex'

export default {
    name: "v-cart-item",
    props: {
        cart_item_data: {
            default() {
                return {}
            }
        }
    },
    computed: {},
    methods: {
        // ...mapActions([
        //     'INCREMENT_CART_ITEM',
        //     'DECREMENT_CART_ITEM'
        // ]),
        decrementItem() {
            this.$emit('decrement')
        },
        incrementItem() {
            this.$emit('increment')
        },
        deleteFromCart() {
            this.$emit('deleteFromCart')
        }
    },
    mounted() {
        //this.$set(this.cart_item_data, 'quantity', 1) //was begins
    }

}
</script>

<style>
    .v-cart-item {
        display: flex;
        flex-wrap: nowrap;
        justify-content: space-between;
        align-items: center;
        box-shadow: 0 0 8px 0 #e0e0e0;
        padding: 16px;
        margin-bottom: 16px;
    }
    .v-cart-item-image {
        max-width: 50px;
    }
    .v-cart-item-quantity {

    }
    .quantity-btn {
        cursor: pointer;
    }
</style>