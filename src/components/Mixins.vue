<template>
  <div>
    <h1>MIXINS</h1>
    <button @click="incrementCounter">Clicked {{ count }}</button>
  </div>
</template>

<script>
import counter from './mixins/counter'

export default {
  name: 'ClickCounter',
  mixins: [counter],
}
</script>

<style>

</style>