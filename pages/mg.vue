<template>
  <div>

    <div v-if="quiz.length === step" class="thanks">
      <h1>Thank you, we will contact you shortly</h1>
      <p v-for="item in quiz">
        {{ item.question }} - <b>{{ item.answer }}</b>
      </p>
      <button @click="reset" >reset quiz</button>
    </div>

    <div v-else class="quiz">
      <h1>{{ quiz[step].question }}</h1>
      <div>
        <button
          v-for="(item, index) in quiz[step].options"
          @click="answer(item)"
          :key="item +'__'+ index">
          {{ item }}
        </button>
      </div>
    </div>
  </div>
</template>

<script>
export default{
  data(){
    return{
      step: 0,
      quiz: [
        {
          question: 'How are you?',
          options: ['good', 'nice', 'hyevo'],
          answer: null
        },
        {
          question: 'Where are you?',
          options: ['usa', 'russia', 'china'],
          answer: null
        },
        {
          question: 'What are you?',
          options: ['men', 'women'],
          answer: null
        }
      ]
    }
  },
  methods: {
    answer(a){
      this.quiz[this.step].answer = a
      this.step = this.step + 1
      localStorage.step = this.step
      localStorage.quiz = JSON.stringify(this.quiz)
    },
    reset(){
      this.step = 0
      this.quiz = [
        {
          question: 'How are you?',
          options: ['good', 'nice', 'hyevo'],
          answer: null
        },
        {
          question: 'Where are you?',
          options: ['usa', 'russia', 'china'],
          answer: null
        },
        {
          question: 'What are you?',
          options: ['men', 'women'],
          answer: null
        }
      ]
    }
  },
  mounted(){
    /*
    if(localStorage.quiz) this.quiz = ??????
    if(localStorage.step) this.step = ??????
    */
  }
}
</script>