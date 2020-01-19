<template>
  <div id="app">
    <p>General Knowledge!</p>
    <ul>
      <li v-for="item in quiz">{{ item.difficulty}}</li>
      
    </ul>

    
    <!-- <div class="question-container">
      <quiz-questions :quiz='quiz'></quiz-questions>
    </div> -->
   



  </div>
  <!--  look at object.key -->
</template>

<script>



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

 

}




</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  text-align: center;
}
</style>
