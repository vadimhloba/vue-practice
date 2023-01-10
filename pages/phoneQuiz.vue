<template>
  <div class="page-phoneQuiz">

    <header>
      <div class="container">
        <div class="header-logo">
          <NuxtLogo/>
        </div>
        <div class="logo-desc">
          <p>US Phone Program</p>
        </div>
      </div>
    </header>

    <div v-if="dowloadComplete" class="thanks">
			<div class="container">
	      <div class="wrapper">
      		<h1>Thank you, we will contact you shortly</h1>
					<div class="answers-text">
      			<p v-for="item in quiz">
      			  {{ item.question }} - <b>{{ item.answer }}</b>
      			</p>
					</div>
      		<button @click="reset">reset quiz</button>
				</div>
			</div>
    </div>

    <section class="preload" v-if="quiz.length === step">
      <div class="container" v-if="!dowloadComplete">
        <h3 v-html="checkProgress"></h3>
        <div class="dowloadPre">
          <div class="counter">{{ dowloadProgress }}%</div>
          <Preloader class="preloader"/>
        </div>
      </div>
    </section>

    <section v-else class="main">
      <div class="container">
        <div class="wrap"></div>
	      <div class="wrapper">

	        <h1>{{step * (100 / quiz.length)}}%</h1>
	        <div class="slider">
	          <div class="tab-move" :style="`width: ${step * (100 / quiz.length)}%;`"></div>
	        </div>

	        <div class="text-main">
	          <h2 v-html="quiz[step].question"></h2>
	          <ul v-if="quiz[step].list">
	            <li v-for="item in quiz[step].list">{{ item }}</li>
	          </ul>
	        </div>

	        <form v-if="step + 1 === quiz.length" @submit.prevent="answer(quiz[step].answer)">
	          <input v-model="quiz[step].answer" type="text" placeholder="Enter Zip Code" required>
	          <input type="submit" value="APPLY NOW">
	        </form>

	        <button
	          v-for="(item, index) in quiz[step].options"
	          @click="answer(item)"
	          :key="`button_${index}`">
	          {{ item }}
	        </button>

	      </div>
      </div>
    </section>
  </div>
</template>

<script>
export default {
  data() {
    return {
      dowloadProgress: 0,
      dowloadComplete: false,
      checkProgress: 'Checking Qualifications',
      step: 0,
      quiz: [
        {
          question: 'Does your household participate in any of the following government programs?',
          list: ['Food Stamps/SNAP', 'Supplemental Security Income (SSI)', 'Veterans Pension benefit or Survivors Pension', 'Medicaid', 'Federal Public Housing Assistance (Section 8)', 'Bureau of Indian Affairs General Assistance (BIA)', 'Tribally Administered Temporary Assistance to Needy Families (Tribal TANF)', 'Tribal Head Start (via income qualifying standard)', 'Food Distribution Program on Indian Reservations (FDPIR)', 'Household Income is 200% or less of the 2022 Federal Poverty Guidelines', 'School Lunch Programs', 'Current Pell Grant Recipients'],
          options: ['Yes', 'No'],
          answer: null
        },
        {
          question: 'Does your household currently have a Lifeline program phone?',
          options: ['Not Sure', 'Yes', 'No'],
          answer: null
        },
        {
          question: 'Once you are qualified for the program, would you like a new phone for free?',
          options: ['I want a free phone', 'I want to keep my smartphone (Receive a free Sim Card)', 'No'],
          answer: null
        },
        {
          question: `Does your current address match what the US Government has on file for your benefits?<br>(If you're not sure what address you have on file, you can call (800) 234-9473 to confirm)`,
          options: ['Not Sure', 'Yes', 'No'],
          answer: null
        },
        {
          question: 'Great! To Get Started, Enter your Zip Code:',
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
      if(this.quiz.length === this.step){
      	const progressInterval = setInterval(() => {
      	  this.dowloadProgress = this.dowloadProgress + 1
      	  this.updateDowloadProgress()
      	  if(this.dowloadComplete){
      	  	clearInterval(progressInterval)
      	  }
      	}, 200);
      }
    },
    reset(){
      this.progress = 0
      this.step = 0
      this.dowloadComplete = false
      this.dowloadProgress = 0
      this.quiz.forEach(item => item.answers = null)
      localStorage.removeItem('step')
      localStorage.removeItem('quiz')
    },
    updateDowloadProgress() {
      if (this.dowloadProgress >= 40 && this.dowloadProgress < 80) {
        this.checkProgress = 'Checking Availability';
      } else if (this.dowloadProgress >= 80 && this.dowloadProgress < 100) {
        this.checkProgress = `You've been matched <br> with Safelink Wireless`;
      } else if (this.dowloadProgress === 100) {
        this.dowloadComplete = true
      } else {
        this.dowloadProgress += 10
      }
    }
  }
}
</script>

<style scoped>
html, body {
	background: radial-gradient(131.56% 209.61% at 25.7% 172.94%, #F9FBFB 0%, #F9FBFB 0%, #3E81B8 100%, #204D8D 100%, #204D8D 100%), radial-gradient(59.31% 93.85% at 50% 57.19%, #F9FBFB 0%, #F9FBFB 0%, #3E81B8 100%, #204D8D 100%, #204D8D 100%), #FFFFFF;
}
button {
	display: block;
	width: 100%;
	max-width: 670px;
	margin: 0 auto;
	height: 54px;
	background: #A91313;
	box-shadow: inset 0px 33px 23px rgba(255, 187, 187, 0.45);
	border-radius: 15px;
	border: 0;
	font-weight: 700;
	font-size: 18px;
	line-height: 22px;
	color: #FFFFFF;
	margin-top: 30px;
}
</style>

<style lang="scss" scoped>
/* page-phoneQuiz START */
.page-phoneQuiz {

	/* header START */
	header {
	  padding: 21px 0 51px;
		.container {
	  	display: flex;
	  	justify-content: flex-start;
	  	align-items: center;
		}
		.logo-desc {
	  	font-weight: 800;
	  	font-size: 23.295px;
	  	line-height: 28px;
	  	text-transform: uppercase;
	  	color: #FFFFFF;
	  	width: 100%;
	  	max-width: 130px;
	  	margin-left: 12px;
		}
	}
	/* header END */

	/* preload START */
	.preload {
		position: relative;
		.container {
	  	justify-content: center;
	  	display: block;
			padding-top: 200px;
	  	padding-bottom: 265px;
		}
		.dowloadPre {
	  	position: relative;
	  	justify-content: center;
	  	align-items: center;
	  	display: flex;
	  	margin-top: 135px;
		}
		h3 {
	  	position: absolute;
	  	font-weight: 700;
	  	font-size: 55px;
	  	line-height: 67px;
	  	color: #FFFFFF;
			top: 10%;
			left: 50%;
			transform: translate(-50%, -10%);
			max-width: 651px;
			white-space: nowrap;
		}
		.counter {
	  	position: absolute;
	  	z-index: 2;
	  	font-weight: 400;
	  	font-size: 61.3081px;
	  	line-height: 70px;
	  	color: #000000;
		}
		.preloader {
	  	display: block;
	  	position: relative;
	  	z-index: 1;
	  	margin: 0 auto;
	  	max-width: 311px;
	  	width: 100%;
		}
	}
	/* preload END */

	/* section main START */
	.main{
	  position: relative;
	  padding-bottom: 80px;
		.container {
	  	display: flex;
	  	justify-content: center;
	  	align-items: center;
		}
		.wrap {
	  	position: relative;
	  	max-width: 745px;
	  	width: 100%;
	  	height: 903px;
	  	margin: 0 auto;
	  	background: #FFFFFF;
	  	border-radius: 14px;
	  	padding: 5px 71px 5px 70px;
	  	color: #000000;
	  	z-index: 1;
		}
		.wrapper {
	  	position: absolute;
	  	z-index: 2;
	  	height: auto;
	  	max-width: 745px;
	  	width: 100%;
		}
		h1 {
	  	display: block;
	  	width: 94px;
	  	max-width: 100%;
	  	font-weight: 500;
	  	font-size: 47.027px;
	  	line-height: 57px;
	  	margin: 0 auto;
		}
		.slider {
	  	position: relative;
	  	margin: 16px 0 51px;
	  	width: 100%;
	  	height: 17.2px;
	  	background: #93CEF6;
	  	border-radius: 12.9323px;
			.tab-move {
	  		position: absolute;
	  		height: 26.28px;
	  		background: #005DC4;
	  		border-radius: 12.9323px;
	  		-webkit-border-radius: 12.9323px;
	  		-moz-border-radius: 12.9323px;
	  		transform: translateY(-50%);
	  		transition: width .3s ease;
	  		left: 0;
	  		top: 50%;
			}
		}
		.text-main {
	  	padding: 0 61px 0 60px;
		}
		h2 {
	  	font-weight: 800;
	  	font-size: 24px;
	  	line-height: 29px;
	  	width: 100%;
		}
		ul {
	  	margin-left: 28px;
	  	padding: 31px 0 20px 10px;
	  	width: 100%;
	  	max-width: 541px;
	  	list-style: outside;
			li {
	  		font-weight: 500;
	  		font-size: 18px;
	  		line-height: 126.9%;
			}
		}
		input[type=text] {
	  	display: block;
	  	margin: 50px auto;
	  	padding: 29px 0 28px 31px;
	  	font-weight: 700;
	  	font-size: 18px;
	  	line-height: 22px;
	  	color: #BFBFBF;
	  	border: 1px solid #BFBFBF;
	  	border-radius: 15px;
	  	max-width: 670px;
	  	width: 100%;
	  	transition: .7s;
			:focus {
	  		border: 1px solid #555;
			}
		}
		input[type=submit] {
	  	display: block;
	  	width: 100%;
	  	max-width: 670px;
	  	margin: 0 auto;
	  	height: 54px;
	  	background: #A91313;
	  	box-shadow: inset 0px 33px 23px rgba(255, 187, 187, 0.45);
	  	border-radius: 15px;
	  	border: 0;
	  	font-weight: 700;
	  	font-size: 18px;
	  	line-height: 22px;
	  	color: #FFFFFF;
	  	margin-top: 30px;
		}
	}
	/* section main END */

	/* div thanks START */
	.thanks {
		text-align: left;
		padding-bottom: 100px;
		.container {
	  	display: flex;
	  	justify-content: center;
	  	align-items: center;
		}
		.wrapper {
	  	max-width: 745px;
	  	width: 100%;
	  	height: auto;
	  	margin: 100px auto 0;
	  	background: #FFFFFF;
	  	border-radius: 14px;
	  	padding: 40px 70px;
	  	color: #000000;
	  	z-index: 1;
		}
		h1 {
			text-align: center;
			font-weight: 700;
	  	font-size: 42px;
	  	line-height: 57px;
		}
		.answers-text {
			display: block;
			max-width: 800px;
			margin: 60px 0;
			p {
				font-weight: 500;
	  		font-size: 17px;
	  		line-height: 22px;
			}
		}
		button {
			font-size: 20px;
		}
	}
	/* div thanks END */
}
/* page-phoneQuiz END */
</style>