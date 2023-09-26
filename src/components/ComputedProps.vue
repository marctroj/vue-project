<template>
  <div class="wrapper">
    <h1>Computed Properties</h1>
    <div v-for="(item, index) in filterProducts" :key="index">
      <p>{{ item.title }}</p>
      <p>${{ item.price }}</p>
    </div>
  </div>
</template>

<script>

export default ({
  name: 'ComputedProps',
  data() {
    return {
      products : [
        {
          id: 1,
          price: 50,
          title: 'Hoodie'
        },
        {
          id: 2,
          price: 20,
          title: 'Tee Shirt'
        },
        {
          id: 3,
          price: 35,
          title: 'Hat'
        }
      ]
    }
  },
  computed: {
    filterProducts() {
      return this.products.filter(item => item.price < 40);
    }
  }
})
</script>

<style>
  .wrapper {
    margin: 50px 0;
  }
</style>