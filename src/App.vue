<template>
  <div id="app">
    <p>General Knowledge!</p>
    <p>{{ quiz[4].correct_answer }}</p>
    <ul>
      <li v-for="item in quiz">{{ item.question}}</li>
    </ul>


  </div>
  <!-- loop over using key, index look at object.key -->
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
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
