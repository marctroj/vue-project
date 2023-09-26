<template>
  <div>
    <h1>{{ name }}</h1>
    <div v-html="showHtml()"></div>
  </div>
</template>

<script>
export default {
  name: 'V-Html',
  data() {
    return {
      name: 'v-html',
      test: 'here is some text'
    }
  },
  methods: {
    showHtml() {
      return `<p>${this.test}</p>`
    }
  }
}
</script>
