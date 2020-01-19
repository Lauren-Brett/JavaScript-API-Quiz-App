<template>
  <div id="app">
    <p>General Knowledge!</p>
      
    <questions-list :quiz='quiz'></questions-list>
    <!-- <question-select :object='selectedQuestion'></question-select> -->


  </div>
  <!--  look at object.key -->
</template>

<script>

import QuestionsList from './components/QuestionsList.vue';
// import QuestionSelect from './components/QuestionSelect.vue';


export default {
  name: 'app',
  data() {
    return {
      quiz: [],
      // selectedQuestion: null
    }
  },


  mounted() {
    fetch('https://opentdb.com/api.php?amount=10&category=9&type=boolean')
      .then(response => response.json())
      .then(quiz => this.quiz = quiz.results )

      // eventBus.$on('question-hit', (object) =>
      // this.selectedQuestion = object)
  },

  components: {
    'questions-list': QuestionsList
    // 'question-select': QuestionSelect 
  }

  }

 






</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;

}
</style>
