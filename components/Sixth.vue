<template>
	
	<section id="preload">

		<h3>Checking Qualifications</h3>

		<div class="container" v-if="!dowloadComplete">
			<div class="counter">{{ dowloadProgress }}%</div>
			<Preloader class="preloader" @:style="{ width: dowloadProgress + '%'}"/>
		</div>

		<div v-else>

		</div>
	</section>

</template>
	
<script scoped>
export default {
	data() {
		return {
			dowloadProgress: 0,
			dowloadComplete: false
		}
	},
	watch: {
		dowloadProgress(newProgress) {
			this.dowloadProgress = newProgress;
		}
	}
}
</script>

<style scoped>
#preload{
	padding-top: 200px;
	padding-bottom: 265px;
}
#preload h3{
	display: block;
	font-weight: 700;
	font-size: 55px;
	line-height: 67px;
	color: #FFFFFF;
	margin: 0 auto;
	max-width: 691px;
	width: 100%;
}
.container{
	position: relative;
	justify-content: center;
	align-items: center;
	display: flex;
	margin-top: 135px;
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
	transition: width 0.5s ease;
}
</style>