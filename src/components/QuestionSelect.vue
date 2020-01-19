<template>
  <div v-if="object">
    <li v-on:click="handleClick">{{ object.difficulty}}</li>
   <!-- // the list is rendered, 
   //display the state of its difficulty   -->
  </div>
</template>

<script>

import { eventBus } from '../main.js';

export default {
    name: 'question-select',
    props: ['object'],
    methods: {
        // handleClick() {
        //   eventBus.$emit('question-hit', this.object)
        }

    }
      
  

 

    




</script>

<style>

</style>