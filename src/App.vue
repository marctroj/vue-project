<template>
  <div>
    <ProductsTest />
    <TransitionTest />
    <VBind />
    <VHtml />
    <VModal />
    <AccordionTest />
    <Mixins />
    <ComputedProps />
    <WatcherTest />
  </div>
</template>

<script>

import TransitionTest from './components/TransitionTest.vue'
import ProductsTest from './components/ProductsTest.vue'
import VBind from './components/VBind.vue'
import VHtml from './components/VHtml.vue'
import VModal from './components/VModal.vue'
import AccordionTest from './components/Accordion.vue'
import Mixins from './components/Mixins.vue'
import ComputedProps from './components/ComputedProps.vue'
import WatcherTest from './components/Watcher.vue'

export default {
  name: 'App',
  components: {
    TransitionTest,
    ProductsTest,
    VBind,
    VHtml,
    VModal,
    AccordionTest,
    Mixins,
    ComputedProps,
    WatcherTest,
  }
}
</script>

<style>
 * {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
 }
</style>
