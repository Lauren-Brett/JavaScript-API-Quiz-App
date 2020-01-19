<template>
<section class="list-questions">
      
    <!-- <ul>
      <difficulty-selected v-for="object in quiz">{{ object.question}}</difficulty-selected>
    </ul> -->



        <!-- display 3 buttons, 
        event on click go to QuestionSelected

        sort the questions by difficuly
            v-if 
           v-for="object in quiz" >{{ object.difficulty}}
        {{ object.question}}

          <li v-on:click="handleClick">{{ quiz.question }} </li>
       -->

   
</section>
  
</template>

<script>

import DifficultySelect from './DifficultySelect.vue';

export default {
    name: 'question-list',
    props: ['quiz'],
    components: {
        'difficulty-selected': DifficultySelect
    }


}
</script>

<style>

</style>