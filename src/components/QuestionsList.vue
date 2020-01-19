<template>
<section class="list-questions">
      
    <ul>
        <li v-for="object in quiz" >{{ object.question }}</li>
         <!-- <question-select v-for="object in quiz" >{{ object.question }}</question-select> -->
    </ul>
   
</section>
  
</template>

<script>

import QuestionSelect from './QuestionSelect.vue';

export default {
    name: 'questions-list',
    props: ['quiz'],
    components: {
        'question-select': QuestionSelect
    }


}
</script>

<style>

</style>