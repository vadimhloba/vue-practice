<template>
	<div>
		<section v-if="showLatestData" class="main">
			<div class="container">
				<div class="wrapper">
					<h1>50%</h1>
					<div class="slider">
						<div class="tab-move"></div>
						<div class="static"></div>
					</div>
					<div class="text-main">
						<h2>Does your household currently have a Lifeline program phone?</h2>
					</div>
					<button @click="switchData" class="not-sure">Not Sure</button>
					<button @click="switchData" class="yes">Yes</button>
					<button @click="switchData" class="no">No</button>
				</div>
			</div>
		</section>
	
		<Third v-if="showNewData"/>
	</div>
</template>

<script scoped>
export default {
    data(){
      return {
          showLatestData: true,
          showNewData: ""
      }
    },
    methods:{
      switchData(){
          this.showLatestData = false;
          this.showNewData = true;
      }
    }
}
</script>

<style scoped>
.main .wrapper{
	padding-top: 212px;
	padding-bottom: 211px;
}
.main .slider .tab-move{
	width: 370px;
}
.main .text-main{
	margin-bottom: 51px;
}
.main .not-sure{
	margin-bottom: 30px;
}

/* key-frames START */
@keyframes lineAnim {
    25% {
        width: 25%;
    }
    50% {
        width: 50%;
    }
}
/* key-frames END */
</style>