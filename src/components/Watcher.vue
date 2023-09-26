<template>
  <div class="wrapper">
    <h1>Watchers</h1>
    <p>Count - {{ count }}</p>
    <button @click="count += 1">Increase</button>
  </div>
</template>

<script>
export default {
  name: 'WatcherTest',
  data() {
    return {
      count: 0,
    }
  },
  watch: {
    count(newValue) {
      if(newValue >= 1) {
        console.log(newValue);
      }
    }
  }
}
</script>

<style>
  .wrapper {
    margin: 50px 0;
  }
</style>
