<template>
<section class="list-questions">
    <ul>
         <question-select v-for="question in questions" :question="question"></question-select>
    </ul>  
</section>
  
</template>

<script>

import QuestionSelect from './QuestionSelect.vue';

export default {
    name: 'questions-list',
    props: ['questions'],
    components: {
        'question-select': QuestionSelect
    }


}
</script>

<style>

</style>