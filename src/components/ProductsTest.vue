<template>
  <div class="product">
    <div class="product__image">
      <img class="img" v-bind:src="image" alt="">
    </div>
    <div class="product__info">
      <h1>{{ product }}</h1>
      <h3 class="product__title">{{ title }}</h3>
      <p class="product__color">{{ color }}</p>
      <p class="product__price">${{ price }}</p>
      <p v-if="inStock">In Stock</p>
      <p v-else>Out Of Stock</p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ProductsTest',
  data() {
    return {
      product: 'Socks',
      image: require('../assets/green-socks.jpg'),
      inStock: true,
      title: 'Crew Socks',
      color: 'green',
      price: '25'
    }
  }
}
</script>

<style>
  .product {
    display: flex;
    margin: 10px;
  }
  .product__info {
    margin-left: 25px;
  }
  .img {
    max-width: 200px;
    width: 100%;
    border: 1px solid gray;
  }
</style>