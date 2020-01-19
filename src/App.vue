<template>
  <div id="app">
    <p>General Knowledge!</p>
      
    <questions-list :questions='questions'></questions-list>
    <!-- <question-select :object='selectedQuestion'></question-select> -->


  </div>
  <!--  look at object.key -->
</template>

<script>

import { eventBus } from './main.js';
import QuestionsList from './components/QuestionsList.vue';
// import QuestionSelect from './components/QuestionSelect.vue';


export default {
  name: 'app',
  data() {
    return {
      questions: [],
    }
  },
  mounted() {
    fetch('https://opentdb.com/api.php?amount=10&category=9&type=boolean')
      .then(response => response.json())
      .then(questions => questions.results.map((question, index) => {
        return { 
          ...question, 
          text: question.question,
          id: Date.now()
        }
      }))
      .then(questions => this.questions = questions)

     eventBus.$on('question-answered', (answer) => {
       
      
     })
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
