<template>
  <div>
    <h1>v-modal</h1>
    <input v-model="name" type="text">
    <p>{{ name }}</p>
  </div>
</template>

<script>
export default {
  name: 'VModal',
  data() {
    return {
      name: null,
    }
  }
}
</script>