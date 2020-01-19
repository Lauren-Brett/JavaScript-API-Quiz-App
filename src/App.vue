<template>
  <div id="app">
    <p>General Knowledge!</p>
    <question-list :quiz='quiz'</question-list>
    <!-- <difficulty-selected ></difficulty-selected> -->

    <ul>
      <difficulty-selected v-for="object in quiz">{{ object.question}}</difficulty-selected>
    </ul>

    
  </div>
  <!--  look at object.key -->
</template>

<script>

import QuestionList from './components/QuestionList.vue';
import DifficultySelect from './components/DifficultySelect.vue';


export default {
  name: 'app',
  data() {
    return {
      quiz: []
    }
  },


  mounted() {
    fetch('https://opentdb.com/api.php?amount=10&category=9&type=boolean')
      .then(response => response.json())
      .then(quiz => this.quiz = quiz.results )
  },

  components: {
    'question-list': QuestionList,
    'difficulty-selected': DifficultySelect

  }

  }

 






</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  text-align: center;
}
</style>
