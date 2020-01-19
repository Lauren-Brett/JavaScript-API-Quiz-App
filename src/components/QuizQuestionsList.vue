<template>
  <section>
      <p>hello</p>
      <!-- <ul>
        
        <quiz-questions-list v-for="item in quiz"> {{ item.question }}</quiz-questions-list>
    
      </ul> -->

  </section>

</template>

<script>
export default {
    name: 'quiz-questions',
    props: ['quiz'],
    components: {
        'quiz-questions-list': QuizQuestionsList
    }

}


</script>

<style>

</style>