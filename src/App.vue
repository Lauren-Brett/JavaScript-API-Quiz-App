<template>
  <div id="app">
    <p>General Knowledge!</p>
    <p>{{ quiz[4].correct_answer }}</p>
    <ul>
      <li v-for="item in quiz">{{ item.question}}</li>
    </ul>


  </div>
  <!--  look at object.key -->
</template>

<script>


export default {
  name: 'app',
  data() {
    return {
      quiz: {}

    }
  },

  mounted() {
    fetch('https://opentdb.com/api.php?amount=10&category=9&type=boolean')
      .then(response => response.json())
      .then(quiz => this.quiz = quiz.results )
  }

}




</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  text-align: center;
}
</style>
