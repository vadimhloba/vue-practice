<template>
	<div>
		<section v-if="showLatestData" class="main">
			<div class="container">
				<div class="wrapper">
					<h1>95%</h1>
					<div class="slider">
						<div class="tab-move"></div>
						<div class="static"></div>
					</div>
					<div class="text-main">
						<h2>Does your current address match what the US Government has on file for your benefits?<br><br>
						(If you're not sure what address you have on file, you can call (800) 234-9473 to confirm)`</h2>
					</div>
					<button @click="switchData" class="not-sure">Not Sure</button>
					<button @click="switchData" class="yes">Yes</button>
					<button @click="switchData" class="no">No</button>
				</div>
			</div>
		</section>
	
		<Fifth v-if="showNewData"/>
	</div>
</template>
	
<script scoped>
export default {
    data() {
        return {
            showLatestData: true,
            showNewData: ""
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
	padding-top: 169px;
	padding-bottom: 168px;
}
.main .slider .tab-move{
	width: 700px;
}
.main .text-main{
	margin-bottom: 50px;
}
.main .not-sure{
	margin-bottom: 30px;
}

/* key-frames START */
@keyframes lineAnim {
    75% {
        width: 75%;
    }
    95% {
        width: 95%;
    }
}
/* key-frames END */
</style>