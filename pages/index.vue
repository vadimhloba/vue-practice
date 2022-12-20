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

		<section v-if="showLatestData" class="main">
			<div class="container">
				<div class="wrapper">
					<h1>25%</h1>
					<div class="slider">
						<div class="tab-move"></div>
						<div class="static"></div>
					</div>
					<div class="text-main">
						<h2>Does your household participate in any of the following government programs?</h2>
						<ul>
							<li>Food Stamps/SNAP</li>
							<li>Supplemental Security Income (SSI)</li>
							<li>Veterans Pension benefit or Survivors Pension</li>
							<li>Medicaid</li>
							<li>Federal Public Housing Assistance (Section 8)</li>
							<li>Bureau of Indian Affairs General Assistance (BIA)</li>
							<li>Tribally Administered Temporary Assistance to Needy Families (Tribal TANF)</li>
							<li>Tribal Head Start (via income qualifying standard)</li>
							<li>Food Distribution Program on Indian Reservations (FDPIR)</li>
							<li>Household Income is 200% or less of the 2022 Federal Poverty Guidelines</li>
							<li>School Lunch Programs</li>
							<li>Current Pell Grant Recipients</li>
						</ul>
					</div>
					<button @click="switchData" class="yes">Yes</button>
					<button @click="switchData" class="no">No</button>
				</div>
			</div>
		</section>
		
		<Second v-if="showNewData"/>

	</div>
</template>

<script>
export default {
		data(){
			return{
				showLatestData: true,
				showNewData: ''
				}
			},
		methods: {
			switchData(){
				this.showLatestData = false;
				this.showNewData = true;
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

/* section main START */
.main{
	padding-bottom: 80px;
}
.main .wrapper{
	max-width: 745px;
	width: 100%;
	margin: 0 auto;
	background: #FFFFFF;
	border-radius: 14px;
	padding: 67px 71px 65px 70px;
	color: #000000;
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
	display: block;
	padding: 16px 0 51px;
}
.main .slider .static{
	width: 100%;
	height: 17.2px;
	background: #93CEF6;
	border-radius: 12.9323px;
}
.main .slider .tab-move{
	content: "";
	position: absolute;
	margin-top: -5px;
	width: 210px;
	height: 26.28px;
	background: #005DC4;
	border-radius: 12.9323px;
	-webkit-border-radius: 12.9323px;
  -moz-border-radius: 12.9323px;
	-webkit-animation: lineAnim 1.3s running infinite;
  -moz-animation: lineAnim 1.3s running infinite;
  animation: lineAnim 1.3s running infinite;
	animation-iteration-count: 1;
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
	padding: 31px 0 50px 10px;
	width: 100%;
	max-width: 541px;
	list-style: outside;
}
.main li{
	font-weight: 500;
	font-size: 18px;
	line-height: 126.9%;
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
}
.main .yes{
	margin-bottom: 30px;
}
/* section main END */

/* key-frames START */
@keyframes lineAnim {
    0% {
        width: 0%;
    }
    25% {
        width: 25%;
    }
}
/* key-frames END */
</style>