<template>
  <section>
     <ul>
        
         <li v-for="item in quiz" :value="item"> 
            {{ item.question }}</li>
    
      </ul>
  </section>

</template>

<script>
export default {
    name: 'quiz-questions',
    props: ['quiz'],

    // components: {
    //     "quiz-questions": QuizQuestionsList,
    // }

}


</script>

<style>

</style>