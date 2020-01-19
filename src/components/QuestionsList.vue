<template>
<section class="list-questions">
      
    <ul>
        <li v-for="object in quiz" >{{ object.question }}</li>
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