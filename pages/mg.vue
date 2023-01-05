<template>
  <div>

    <div class="progress">
      <b>{{step * (100 / quiz.length)}}%</b>
      <span :style="`width: ${step * (100 / quiz.length)}%;`"></span>
    </div>

    <div v-if="quiz.length === step" class="thanks">
      <h1>Thank you, we will contact you shortly</h1>
      <p v-for="item in quiz">
        {{ item.question }} - <b>{{ item.answer }}</b>
      </p>
      <button @click="reset" >reset quiz</button>
    </div>

    <div v-else class="quiz">
      <h1 v-html="quiz[step].question"></h1>
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

<script scoped>
export default{
  data(){
    return{
      step: 0,
      quiz: [
        {
          question: 'Does your household participate in any of the following government programs?',
          options: ['Yes', 'No'],
          answer: null
        },
        {
          question: 'Does your household currently have a Lifeline program phone?',
          options: ['Not sure', 'Yes', 'No'],
          answer: null
        },
        {
          question: 'Once you are qualified for the program, would you like a new phone for free?',
          options: ['I want a free phone', 'I want to keep my smartphone (Receive a free Sim Card)', 'No'],
          answer: null
        },
        {
          question: `Does your current address match what the US Government has on file for your benefits? <br><br>(If you're not sure what address you have on file, you can call (800) 234-9473 to confirm)`,
          options: ['Not sure', 'Yes', 'No'],
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
      this.quiz.forEach(item => item.answers = null)
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

<style lang="scss" scoped>
.progress{
  height: 17.2px;
  background: #93CEF6;
  border-radius: 12.9323px;
  width: 100%;
  position: relative;
  margin-top: 100px;
  span{
    position: absolute;
    height: 26.28px;
    left: 0;
    top: 50%;
    transform: translateY(-50%);
    background: #005DC4;
    border-radius: 12.9323px;
    transition: width .3s ease;
  }
  b{
    font-weight: 500;
    font-size: 47.027px;
    line-height: 57px;
    color: #000000;
    position: absolute;
    left: 50%; top: -100%;
    transform: translate(-100%, -100%);
  }
}
</style>