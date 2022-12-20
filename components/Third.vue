<template>
	<div>
		<section v-if="showLatestData" class="main">
			<div class="container">
				<div class="wrapper">
					<h1>75%</h1>
					<div class="slider">
						<div class="tab-move"></div>
						<div class="static"></div>
					</div>
					<div class="text-main">
						<h2>Once you are qualified for the program, would you like a new phone for free?</h2>
					</div>
					<button @click="switchData" class="free-phone">I want a free phone</button>
					<button @click="switchData" class="free-card">I want to keep my smartphone (Receive a free Sim Card)</button>
					<button @click="switchData" class="no">No</button>
				</div>
			</div>
		</section>
	
		<Fourth v-if="showNewData"/>
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
	padding-top: 212px;
	padding-bottom: 212px;
}
.main .slider .tab-move{
	width: 560px;
}
.main .text-main{
	margin-bottom: 50px;
}
.main .free-phone{
	margin-bottom: 30px;
}
.main .free-card{
	margin-bottom: 30px;
}

/* key-frames START */
@keyframes lineAnim {
    50% {
        width: 50%;
    }
    75% {
        width: 75%;
    }
}
/* key-frames END */
</style>