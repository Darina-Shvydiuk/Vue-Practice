<template>
<div class="product-card">
  <img :src="imgUrl" width="300px" alt="table">
<div class="product-card__info">
<h2>{{ title }}</h2>
<p class="price">{{ price }}$</p>
<p class="count">Available for delivery{{ count }}</p>
<button type="button" @click="addToBasket">Add to shopping cart</button>
</div>
</div>
</template>
<script>
export default {
  name: 'ProductCard',
  props: {
    title: {
      type: String,
      validator (value) {
        return value.length < 50
      }
    },
    price: {
      type: Number,
      required: true
    },
    imgUrl: {
      type: String,
      default: 'https://ir.ozone.ru/s3/multimedia-n/c200/6308871311.jpg'
    },
    count: {
      type: Number,
      default: 0
    }
  },
  methods: {
    addToBasket () {
      this.$emit('addToBasket')
    }
  }
}
</script>
<style lang="scss" scoped>
.product-card {
  border: 1px solid rgb(211, 211, 211);
  padding: 20px 15px;
  &__info {
    margin-top: 20px;
    h2, .price {
      font-weight: 500;
    }
    .count {
      color: rgb(143, 143, 143);
    }
    button {
      background-color: rgb(221, 56, 56);
      color: #fff;
      border: none;
      border-radius: 4px;
      padding: 8px 14px;
      display: block;
      cursor: pointer;
      margin-top: 20px;
      margin: auto;
    }
  }
}
</style>
