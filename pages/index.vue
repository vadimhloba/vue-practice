<template>
	<div id="index">

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
      <h1>Thank you, we will contact you shortly</h1>
      <p v-for="item in quiz">
        {{ item.questions }} - <b>{{ item.answer }}</b>
      </p>
      <button @click="reset">reset quiz</button>
    </div>
		
		<section class="preload" v-if="quiz.length === step">
			<div class="container" v-if="!dowloadComplete">
				<h3>{{ checkProgress }}</h3>
				<div class="dowloadPre">
					<div class="counter">{{ dowloadProgress }}%</div>
					<Preloader class="preloader" :style="{ width: dowloadProgress + '%'}"/>
				</div>
			</div>
		</section>

		<section v-else class="main">
			<div class="container">
				<div class="wrapper"></div>
				<div class="wrap">

					<h1>{{step * (100 / quiz.length)}}%</h1>

					
					<div class="slider">
						<div class="tab-move" :style="`width: ${step * (100 / quiz.length)}%;`"></div>
					</div>
					

					<div class="text-main">
						<h2
							v-for="(item, index) in quiz[step].questions"
							:key="item +'__'+ index">
							{{ item }}
						</h2>
						<ul>
							<li 
								v-for="(item, index) in quiz[step].massages"
								:key="item +'__'+ index">
								{{ item }}
							</li>
						</ul>
					</div>

					<form v-for="(item) in quiz[step].code"
						@submit.prevent="answer(item)"
						:key="item">
						<input v-model="enterCode" type="text" placeholder="Enter Zip Code" required>
						<input type="submit" value="APPLY NOW APPLY NOW">
					</form>

					<button
						v-for="(item, index) in quiz[step].options"
						@click="answer(item)"
						:key="item +'__'+ index">
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
					questions: ['Does your household participate in any of the following government programs?'],
					massages: ['Food Stamps/SNAP', 'Supplemental Security Income (SSI)',
					'Veterans Pension benefit or Survivors Pension', 'Medicaid',
					'Federal Public Housing Assistance (Section 8)',
					'Bureau of Indian Affairs General Assistance (BIA)',
					'Tribally Administered Temporary Assistance to Needy Families (Tribal TANF)',
					'Tribal Head Start (via income qualifying standard)',
					'Food Distribution Program on Indian Reservations (FDPIR)',
					'Household Income is 200% or less of the 2022 Federal Poverty Guidelines',
					'School Lunch Programs', 'Current Pell Grant Recipients'],
					options: ['Yes', 'No'],
					answer: null
				},
				{
					questions: ['Does your household currently have a Lifeline program phone?'],
					options: ['Not Sure', 'Yes', 'No'],
					answer: null
				},
				{
					questions: ['Once you are qualified for the program, would you like a new phone for free?'],
					options: ['I want a free phone',
					'I want to keep my smartphone (Receive a free Sim Card)', 'No'],
					answer: null
				},
				{
					questions: ['Does your current address match what the US Government has on file for your benefits?',
					'(If you`re not sure what address you have on file, you can call (800) 234-9473 to confirm)`'],
					options: ['Not Sure', 'Yes', 'No'],
					answer: null
				},
				{
					questions: ['Great! To Get Started, Enter your Zip Code:'],
					code: [''],
					answer: null
				}
			]
		}
  },
	created() {
		setInterval(this.updateDowloadProgress, 2000);
	},
  methods: {
  	answer(a){
			this.quiz[this.step].answer = a
			this.step = this.step + 1
			localStorage.step = this.step
			localStorage.quiz = JSON.stringify(this.quiz)
		},
		reset(){
			this.progress = 0
  	  this.step = 0
  	  this.quiz.forEach(item => item.answers = null)
  	},
		updateDowloadProgress() {
			if (this.dowloadProgress >= 100) {
				this.dowloadComplete = true
			} else {
				this.dowloadProgress += 10
			}

			// Update the progressText data property based on the progress
      if (this.dowloadProgress >= 40) {
        this.checkProgress = 'Checking Availability';
      }
      if (this.dowloadProgress >= 80) {
        this.checkProgress = 'You\'ve been matched with Safelink Wireless';
      }

		}
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@500;700;800&display=swap');

html, body{
	font-size: 14px;
	line-height: 1.2;
	margin: 0;
	padding: 0;
}
.container{
	width: 100%;
	margin-right: auto;
	margin-left: auto;
	padding: 0 15px;
}
@media (min-width: 576px){
	.container {
    width: 540px;
	}
}
@media(min-width:768px){
	.container{
		width: 760px;
	}
}
@media(min-width:992px){
	.container{
		width: 990px;
	}
}
@media(min-width:1200px){
	.container{
		width: 1190px;
	}
}

/* #index START */
#index{
	background: radial-gradient(131.56% 209.61% at 25.7% 172.94%, #F9FBFB 0%, #F9FBFB 0%, #3E81B8 100%, #204D8D 100%, #204D8D 100%), radial-gradient(59.31% 93.85% at 50% 57.19%, #F9FBFB 0%, #F9FBFB 0%, #3E81B8 100%, #204D8D 100%, #204D8D 100%), #FFFFFF;
	font-family: 'Montserrat', sans-serif;
}
/* #index END */

/* header START */
header{
	padding: 21px 0 51px;
}
header .container{
	display: flex;
	justify-content: flex-start;
	align-items: center;
}
header .logo-desc{
	font-weight: 800;
	font-size: 23.295px;
	line-height: 28px;
	text-transform: uppercase;
	color: #FFFFFF;
	width: 100%;
	max-width: 130px;
	margin-left: 12px;
}
/* header END */

/* preload START */
.preload{
	padding-top: 200px;
	padding-bottom: 265px;
}
.preload .container{
	justify-content: center;
	display: block;
}
.preload .dowloadPre{
	position: relative;
	justify-content: center;
	align-items: center;
	display: flex;
	margin-top: 135px;
}
.preload h3{
	display: block;
	font-weight: 700;
	font-size: 55px;
	line-height: 67px;
	color: #FFFFFF;
	margin: 0 auto;
	max-width: 691px;
	width: 100%;
}
.counter{
	position: absolute;
	z-index: 2;
	font-weight: 400;
	font-size: 61.3081px;
	line-height: 70px;
	color: #000000;
}
.preloader{
	display: block;
	position: relative;
	z-index: 1;
	margin: 0 auto;
	max-width: 311px;
	width: 100%;
	animation: 6s ease-in-out infinite preloader-animation;
}
/* preload END */

/* section main START */
.main{
	position: relative;
	padding-bottom: 80px;
}
.main .container{
	display: flex;
	justify-content: center;
	align-items: center;
}
.main .wrapper{
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
.main .wrap{
	position: absolute;
	z-index: 2;
	height: auto;
	max-width: 745px;
	width: 100%;
}
.main h1{
	display: block;
	width: 94px;
	max-width: 100%;
	font-weight: 500;
	font-size: 47.027px;
	line-height: 57px;
	margin: 0 auto;
}
.main .slider{
	position: relative;
	margin: 16px 0 51px;
	width: 100%;
	height: 17.2px;
	background: #93CEF6;
	border-radius: 12.9323px;
}
.main .slider .tab-move{
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

.main .text-main{
	padding: 0 61px 0 60px;
}
.main h2{
	font-weight: 800;
	font-size: 24px;
	line-height: 29px;
	width: 100%;
}
.main ul{
	margin-left: 28px;
	padding: 31px 0 20px 10px;
	width: 100%;
	max-width: 541px;
	list-style: outside;
}
.main li{
	font-weight: 500;
	font-size: 18px;
	line-height: 126.9%;
}
.main input[type=text]{
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
}
input[type=text]:focus{
  border: 1px solid #555;
}
.main input[type=submit]{
	display: block;
	cursor: pointer;
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
.main button{
	display: block;
	cursor: pointer;
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
/* section main END */

/* key-frames START */
@keyframes preloader-animation {
  0% {
    transform: rotate(0deg);
  }
  100% {
    transform: rotate(360deg);
  }
}
/* key-frames END */
</style>