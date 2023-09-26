<template>
  <div class="accordion">
    <h1>Accordion</h1>
    <div v-for="(faq, index) in faqs" :key="index">
      <div @click="toggleOpen(index)" class="accordion__question">{{ faq.question}}</div>
      <transition name="slide">
        <div
          class="accordion__answer"
          v-if="faq.open"
        >
          {{ faq.answer }}
        </div>
      </transition>
    </div>
  </div>
</template>

<script>
export default {
  name: 'AccordionTest',
  data() {
    return {
      faqs: [
        {
          question: 'Question One',
          answer: 'One Lorem ipsum dolor sit amet consectetur adipisicing elit. Nihil, eaque? One Lorem ipsum dolor sit amet consectetur adipisicing elit. Nihil, eaque? One Lorem ipsum dolor sit amet consectetur adipisicing elit. Nihil, eaque? One Lorem ipsum dolor sit amet consectetur adipisicing elit. Nihil, eaque?',
          open: false
        },
        {
          question: 'Question Two',
          answer: 'Two Lorem ipsum dolor sit amet consectetur adipisicing elit. Nihil, eaque? Two Lorem ipsum dolor sit amet consectetur adipisicing elit. Nihil, eaque? Two Lorem ipsum dolor sit amet consectetur adipisicing elit. Nihil, eaque? Two Lorem ipsum dolor sit amet consectetur adipisicing elit. Nihil, eaque?',
          open: false
        }
      ]
    }
  },
  methods: {
    toggleOpen(index) {
      this.faqs.map((faq, i) => {
        index === i ? faq.open = !faq.open : faq.open = false;
      })
    }
  }
}
</script>

<style>
  .accordion {
    border-top: 1px solid black;
    padding: 10px 0;
    margin: 50px 0;
    max-width: 500px;
  }

  .accordion__question {
    margin-bottom: 4px;
    cursor: pointer;
    display: inline-block;
    border: 1px solid black;
    padding: 2px 10px;
  }

  .accordion__answer {
    border-bottom: 1px solid black;
  }

  /**
  * Transitions
  */
  .slide-enter-from {
    overflow: hidden;
    max-height: 0;
    visibility: hidden;
  }

  .slide-enter-to {
    max-height: 600px;
    overflow: hidden;
    visibility: visible;
  }

  .slide-enter-active,
  .slide-leave-active {
    transition: all 300ms ease-in-out;
  }

  .slide-leave-from {
    max-height: 600px;
    overflow: hidden;
    visibility: visible;
  }

  .slide-leave-to {
    overflow: hidden;
    max-height: 0;
    visibility: hidden;
  }
  
</style>