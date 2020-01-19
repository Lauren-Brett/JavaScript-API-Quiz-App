<template>
  <section class="list-questions">
    <ul>
      <question-select
        v-for="question in questions"
        :question="question"
        :isCorrectAnswer="isAnsweredCorrectly(question.id)"
      ></question-select>
    </ul>
  </section>
</template>

<script>

import QuestionSelect from './QuestionSelect.vue';
import { eventBus } from '../main'

export default {
    name: 'questions-list',
    props: ['questions'],
    data: function(){
        return {
            answers: []
        }
    },
    components: {
        'question-select': QuestionSelect
    },
    mounted: function(){
        eventBus.$on('question-answered', (answer) => {
            this.answers.push(answer)
        })
    },
    methods: {
        isAnsweredCorrectly: function(questionId){
            let hasBeenAnswered = false
            const foundAnswer = this.answers.find(answer => answer.id === questionId)
            if (foundAnswer) hasBeenAnswered = true
            if (!hasBeenAnswered) {
                return null
            }
            const foundQuestion = this.questions.find(question => question.id === questionId)
            let isCorrect = false
            if (foundAnswer.choice === foundQuestion.correct_answer) {
                return true
            } else {
                return false
            }
        }
    }

}
</script>

<style>
</style>