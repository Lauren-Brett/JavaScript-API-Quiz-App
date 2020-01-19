<template>
    <li v-if="question">
      <p>{{ question.text }}</p>
      <button v-on:click="handleClick('True')">True</button>
      <button v-on:click="handleClick('False')">False</button>
    </li>
   <!-- // the list is rendered, 
   //display the state of its difficulty   -->
</template>

<script>

import { eventBus } from '../main.js';

export default {
    name: 'question-select',
    props: ['question'],
    methods: {
        handleClick(choice) {
          eventBus.$emit('question-answered', {
            choice: choice,
            questionId: this.question.id 
          })
        }    
        //   eventBus.$emit('question-hit', this.object)
    }

  }
      
  

 

    




</script>

<style>

</style>