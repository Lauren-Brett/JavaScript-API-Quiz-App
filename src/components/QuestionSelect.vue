<template>
    <li v-if="question">
      <p v-bind:class="status">{{ question.text }}</p>
      <button v-on:click="handleClick('True')">True</button>
      <button v-on:click="handleClick('False')">False</button>
    </li>

</template>

<script>

import { eventBus } from '../main.js';

export default {
    name: 'question-select',
    props: ['question'],
    data: function(){
      return {
        isCorrectAnswer: null
      }
    },
    methods: {
        handleClick(choice) {
          this.isCorrectAnswer = this.question.correct_answer === choice

          eventBus.$emit('question-answered', {
            choice: choice,
            questionId: this.question.id 
          })
        }     
    },
    computed: {
      status: function(){
        if ( this.isCorrectAnswer === true ){
          return "right"
        } else if ( this.isCorrectAnswer === false ) {
          return "wrong"
        } else {
          return ""
        }
      }
    }
  }
      
</script>

<style>
  .right {
    color: green;
  }

  .wrong {
    color: red;
  }

</style>