<template>
<div class="product-list">
  <div class="flex top-information">
<h1>Desks</h1>
<search-goods @search="searchProducts"/>
{{ searchText }}
  </div>
  <ul class="list default flex">
<li v-for="(product,index) in products" :key="index">
<product-card
:title="product.title"
:img-url="product.imgUrl"
:price="product.price"
:count="product.count"
@addToBasket="addToBasket(index)"
/>
</li>
  </ul>
</div>
</template>
<script>
import ProductCard from './ProductCard.vue'
import SearchGoods from './SearchGoods.vue'
export default {
  name: 'ProductList',
  components: { ProductCard, SearchGoods },
  data () {
    return {
      searchText: '',
      products: [
        {
          title: 'Table Jim',
          price: 20,
          imgUrl: 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcT_tC9lkPLkZ-o8VRH6oeDOQbU--nkSPQC4jttzF7Li_0urhbVbiwpP6qHDi5GA4W4gJaM&usqp=CAU',
          count: 30
        },
        {
          title: 'Table Monaco',
          price: 50,
          imgUrl: 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQRTv4Eo_7fqTD-5oA4wLCOrYhXHfuoPAlQ1cU8CWRsF22pa7qgEBW9bgQMuPnlrjItIm4&usqp=CAU',
          count: 20
        },
        {
          title: 'Table Tod',
          price: 30,
          imgUrl: 'https://ir.ozone.ru/s3/multimedia-n/c200/6308871311.jpg',
          count: 10
        }
      ]
    }
  },
  methods: {
    addToBasket (index) {
      console.log(index)
    },
    searchProducts (searchText) {
      console.log('Load goods ' + '' + searchText)
    }
  }
}
</script>
<style lang="scss" scoped>
li {
  margin-right: 20px;
}
.top-information {
  align-items: center;
  margin-top:22px;
  h1 {
    margin-bottom: 0;
  }
  button {
    background-color: rgb(221, 56, 56);
    color: #fff;
    border: none;
    border-radius: 4px;
    padding: 8px 14px;
    display: block;
    cursor: pointer;
    margin-left: 10px;
  }
  margin-bottom: 22px;
}
</style>
