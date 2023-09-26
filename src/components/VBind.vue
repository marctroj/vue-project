<template>
  <div>
    <h1>{{ name }}</h1>

    <h2>Class Binding</h2>
    <div 
      v-for="(item, index) in testArray" :key="index"
      @click="toggleClass(item)"
    >
      <p 
        v-bind:class="{ 'header' : item.hasRed }"
        class="static-class"
      >
        {{ item.name }}
      </p>
    </div>

    <h1 v-bind:style="{ color: redColor}">Style Binding</h1>
    <h1 v-bind:style="headerObject">Style Object</h1>

    <p v-bind:style="collectionStyles('title')">Title</p>
    <p v-bind:style="collectionStyles('price')">Price</p>
    <p v-bind:style="collectionStyles('info')">Description</p>

    <!-- <h2>Array Classes</h2>
    <div v-for="(item, index) in testArray" :key="index">
      <p 
        v-bind:class="[
          item.hasRed ? 'header strike-out' : 'other-class'
        ]"
        class="static-class"
      >
        {{ item.name }}
      </p>
    </div> -->
    <a v-bind:href="url">LINK</a>
  </div>
</template>

<script>
export default {
  name: 'VBind',
  data() {
    return {
      name: 'v-bind',
      testArray: [
        { name: 'One', hasRed: false },
        { name: 'Two', hasRed: true },
        { name: 'Three', hasRed: true }
      ],
      url: 'https://www.google.com',
      redColor: 'red',
      headerObject: {
        color: 'gray',
        padding: '20px 0',
      },
      productStyles: {
        title: {
          color: 'red',
          size: '30'
        },
        price: {
          color: 'blue',
          size: '24'
        },
        info: {
          color: 'gray',
          size: '16'
        }
      }
    }
  },
  methods: {
    toggleClass(item) {
      item.hasRed = !item.hasRed;
      console.log(item.hasRed);
    },
    collectionStyles(type) {
      const styleObj = this.productStyles[type];

      let styles = '';

      if (styleObj.color) {
        styles += `color: ${styleObj.color};`
      }
      if (styleObj.size) {
        styles += `font-size: ${styleObj.size}px;`
      }

      return styles;
    }
  },
  computed: {
    filteredData() {
      return this.testArray.filter(item => item.hasRed) 
    }
  }
}
</script>

<style>
  .header {
    color: red;
  }
  .static-class {
    font-weight: bolder;
    cursor: pointer;
    display: inline-block;
    margin: 4px 0;
  }
  .strike-out {
    text-decoration: line-through;
  }
  .other-class {
    font-style: italic;
  }
</style>