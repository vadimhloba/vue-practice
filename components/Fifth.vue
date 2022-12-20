<template>
	<div>
		<section v-if="showLatestData" class="main">
			<div class="container">
				<div class="wrapper">
					<h1>100%</h1>
					<div class="slider">
						<div class="tab-move"></div>
						<div class="static"></div>
					</div>
					<div class="text-main">
						<h2>Great! To Get Started, Enter your Zip Code:</h2>
					</div>
					<form @submit.prevent="switchData">
						<input type="text" placeholder="Enter Zip Code" required>
						<input type="submit" value="APPLY NOW APPLY NOW" class="apply-now">
					</form>
				</div>
			</div>
		</section>
	
		<Sixth v-if="showNewData"/>
	</div>
</template>

<script scoped>
export default {
    data() {
        return {
            showLatestData: true,
            showNewData: "",
        };
    },
    methods: {
        switchData() {
            this.showLatestData = false;
            this.showNewData = true;
        }
    }
}
</script>
	
<style scoped>
.main .wrapper{
	padding-top: 224px;
	padding-bottom: 223px;
}
.main .slider .tab-move{
	width: 100%;
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
input[type=text]:focus {
  border: 1px solid #555;
}
.main .apply-now{
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
.main .not-sure{
	margin-bottom: 30px;
}
/* key-frames START */
@keyframes lineAnim {
    95% {
        width: 95%;
    }
    100% {
        width: 100%;
    }
}
/* key-frames END */
</style>