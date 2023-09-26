<template>
  <transition name="fade">
    <div v-if="showP" class="hello">Hello</div>
  </transition>

  <button @click="showP = !showP">Toggle</button>
</template>

<script>
export default {
  name: 'TransitionTest',
  data() {
    return {
      showP: true,
    }
  }
}
</script>

<style>
  .fade-enter-from {
    opacity: 0;
  }
  .fade-enter-to {
    opacity: 1;
  }
  .fade-enter-active,
  .fade-leave-active {
    transition: opacity 400ms ease;
  }
  .fade-leave-from {
    opacity: 1;
  }
  .fade-leave-to {
    opacity: 0;
  }
</style>