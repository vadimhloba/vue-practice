<template>
	<div class="page-index">

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

		<section class="free-smartphone">
			<div class="container">
				<div class="col-one">
					<h1>Get A <b>Free Smartphone</b> From The Government</h1>
					<h2>If you qualify, you will receive:</h2>
					<ul>
						<li>FREE smartphone*</li>
						<li>FREE unlimited talk</li>
						<li>FREE unlimited texting</li>
						<li>FREE high-speed data</li>
						<li>PLUS free hotspot service</li>
					</ul>
					<button>SEE IF YOU QUALIFY >></button>
					<p>* You may also keep your current compatible smartphone and
						phone number and receive a program SIM for free service.</p>
				</div>
				<div class="col-two">
					<img src="img/phone-pic.png" class="phone-pic"/>
				</div>
			</div>
		</section>

		<section class="cov-details">
			<div class="container">
				<div class="col-one">
					<h1>Coverage details</h1>
					<h2>Eligible customers can now receive free monthly benefits through the ACP
						program while keeping their device and number. With Unlimited Talk & Text
						plus Calls to Canada & Mexico, 25GB Total of High-Speed Data & up to 5GB
						of Hotspot Data, you can stay connected to loved ones, virtual classrooms,
						and Zoom meetings.</h2>
					<div class="point">
						<div class="row-one">
							<img src="img/data-pic.png" class="data-pic">
							<p>FREE 25GB of High-
								Speed Data AND UP TO 5GB
								of Hotspot Data**
								Compatible device required.</p>
						</div>
						<div class="row-two">
							<img src="img/talk-pic.png" class="talk-pic">
							<p>Unlimited Talk & Text + Calls
								to Canada & Mexico* + FREE
								Smartphone or SIM Card
								Most GSM Smartphones are compatible.</p>
						</div>
					</div>
					<button>GET FREE UNLIMITED TALK &TEXT + DATA EVERY MONTH >></button>
				</div>
				<div class="col-two">
					<img src="img/call-pic.png" class="call-pic"/>
				</div>
			</div>
		</section>

		<section class="get-started">
			<div class="container">
				<div class="column">
					<h1>Get started.</h1>
					<h2>Take advantage of this limited-time government assistance today with a
						quick and easy verification and application process.
						Simply follow these steps:</h2>
					<div class="point">
						<div class="row-one">
							<div class="wrapper">
								<h1 class="bg-number">1</h1>
								<h2>CONFIRM ELIGIBILITY</h2>
								<p>Confirm if anyone in your household participates in a qualifying program.</p>
							</div>
						</div>
						<div class="row-two">
							<div class="wrapper">
								<h1 class="bg-number">2</h1>
								<h2>APPLY FOR ACP</h2>
								<p>Provide the necessary information or fill out your application.</p>
							</div>
						</div>
						<div class="row-three">
							<div class="wrapper">
								<h1 class="bg-number">3</h1>
								<h2>ENJOY YOUR SERVICE</h2>
								<p>Receive a notification of your approval within 48 hours.</p>
							</div>
						</div>
					</div>
					<button>CONFIRM ELIGIBILITY >></button>
				</div>
			</div>
		</section>
		
		<section class="check-qualify">
			<div class="container">
				<div class="column">
					<h1>Check if you qualify.</h1>
					<h2>You may qualify for ACP if you meet one
						or more of the following criteria:</h2>
					<div class="point">
						<div class="row-one">
							<div class="wrapper">
								<img src="img/cross-pic.png" class="cross-pic">
								<h1>GOVERNMENT ASSISTANCE</h1>
								<p>You participate in certain assistance programs
									such as SNAP, Medicaid, or LifeLine.</p>
							</div>
						</div>
						<div class="row-two">
							<div class="wrapper">
								<img src="img/apple-pic.png" class="apple-pic">
								<h1>RECEIVED A PELL GRANT</h1>
								<p>You received a Federal Pell Grant during the current award year.</p>
							</div>
						</div>
						<div class="row-three">
							<div class="wrapper">
								<img src="img/dollar-pic.png" class="dollar-pic">
								<h1>LUNCH PROGRAMS</h1>
								<p>You received approval for benefits under the free
									and reduced-price school lunch program.</p>
							</div>
						</div>
					</div>
					<button>CHECK ELIGIBILITY >></button>
				</div>
			</div>
		</section>

		<section class="faq">
			<div class="container">
				<div class="column">
					<h1>FREQUENTLY ASKED QUESTIONS`</h1>
					<div class="point">
						<div class="row-one">
							<!-- add style marks -->
							<ul>
								<li>IS THIS A SCAM?</li>
								<p>No. This is an official program provided
									by the United States Federal Government.
									Specifically, the LifeLine ACP.</p>
								<li>What is the Affordable Connectivity Program (ACP)?</li>
								<li>Am I eligible?</li>
								<li>How do I apply for ACP?</li>
							</ul>
						</div>
						<div class="row-two">
							<ul>
								<li>What does "one per household" mean?</li>
								<li>I was affected by the COVID-19 pandemic
									and lost my job. Am I eligible for ACP?`</li>
								<li>Are there any restrictions for this program?</li>
							</ul>
						</div>
					</div>
					<button>CONFIRM ELIGIBILITY>></button>
				</div>
			</div>
		</section>

		<section class="map">
			<div class="container">
				<div class="column">
					<UsMap class="map-pic"/>
					<button>CONFIRM ELIGIBILITY>></button>
				</div>
			</div>
		</section>

		<footer>
			<div class="container">
				<div class="column">
					<p>Video typically streams at DVD quality.<br>
						*Dial up to 15 unique landline and mobile numbers
						(in select destinations only, which are subject to change at any time)
						each 30-day cycle. Calls must <br> originate from the US or Puerto Rico;
						no international roaming allowed. <br> **Your Hotspot or BYOP service
						can only be activated where Service is available, offered, and supported. <br>
						Unused balance will not carry over from month to month. A month equals 30 days.</p>
				</div>
			</div>
		</footer>

	</div>
</template>

<script scoped>
export default{

}
</script>

<style>
/* Add more font-styles */
@import url('https://fonts.googleapis.com/css2?family=Montserrat:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap');

html, body {
  font-size: 14px;
  line-height: 1.2;
  margin: 0;
  padding: 0;
	height: auto;
	font-family: 'Montserrat', sans-serif;
}
.container {
  width: 100%;
  margin-right: auto;
  margin-left: auto;
  padding: 0 15px;
}
input[type=text], input[type=submit], button{
	cursor: pointer;
}
img {
	display: block;
	max-width: 100%;
	height: auto;

}
button {
	display: block;
	padding: 26px 0 25px;
	width: 100%;
	margin: 0 auto;
	background: #A91313;
	box-shadow: inset 0px 33px 23px rgba(255, 187, 187, 0.45);
	border-radius: 15px;
	border: 0;
	font-weight: 700;
	font-size: 24px;
	line-height: 29px;
	color: #FFFFFF;
}
@media (min-width: 576px) {
  .container {
    width: 540px;
  }
}
@media(min-width:768px) {
  .container {
    width: 760px;
  }
}
@media(min-width:992px) {
  .container {
    width: 990px;
  }
}
@media(min-width:1200px) {
  .container {
    width: 1190px;
  }
}
</style>

<style lang="scss" scoped>

p, ul, li, h1, h2, h3, b {
	margin: 0;
}

/* #index START */
.page-index {
	background: radial-gradient(207.45% 148.69% at 43.02% 104.62%, #F9FBFB 0%, #F9FBFB 0%, #3E81B8 100%, #204D8D 100%, #204D8D 100%) /* warning: gradient uses a rotation that is not supported by CSS and may not behave as expected */, #FFFFFF;
	/* header START */
	header {
	  padding: 21px 0 56px;
		background: #0054AC;
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

	/* free-smartphone START */
	.free-smartphone {
		padding-bottom: 120px;
		background: #0054AC;
		.container {
			display: flex;
			justify-content: center;
			align-items: center;
		}
		.col-one {
			width: calc(100% / 2);
			color: #FFFFFF;
			h1 {
				font-weight: 800;
				font-size: 69.6186px;
				line-height: 85px;
				text-transform: uppercase;
				min-width: 778.74px;
				width: 100%;
				b {
					font-weight: 800;
					color: #B52A2A;
				}
			}
			h2 {
				font-weight: 700;
				font-size: 34px;
				line-height: 41px;
				margin: 40px 0 34px;
			}
			ul {
				font-weight: 500;
				font-size: 24px;
				line-height: 29px;
				li {
					margin-bottom: 17px;
				}
				li:last-child {
					margin-bottom: 0;
				}
				li::marker {
					font-size: 22px;
				}
			}
			button {
				max-width: 413px;
				justify-content: start;
				margin: 46px 0 30px;
			}
			p {
				max-width: 524px;
				width: 100%;
				font-weight: 400;
				font-size: 18px;
				line-height: 22px;
			}
		}
		.col-two {
			position: relative;
			width: calc(100% / 2);
			.phone-pic {
				position: absolute;
				top: 0;
				left: 0;
				transform: translate(15%, -45%);
			}
		}
	}
	/* free-smartphone END */

	/* cov-details START */
	.cov-details {
		padding: 179px 0 120px;
		.container {
			display: flex;
			justify-content: center;
			align-items: center;
		}
		.col-one {
			width: 713px;
			h1 {
				font-weight: 800;
				font-size: 42px;
				line-height: 51px;
			}
			h2 {
				font-weight: 400;
				font-size: 22px;
				line-height: 27px;
				margin: 60px 0 40px;
			}
			.point {
				display: flex;
				align-items: start;
				p {
						max-width: 257px;
						width: 100%;
						font-weight: 400;
						font-size: 17px;
						line-height: 21px;
						margin-left: 15px;
					}
					.data-pic {
						max-width: 30.48px;
						width: 100%;
						height: 51px;
					}
					.talk-pic {
						max-width: 46.92px;
						width: 100%;
						height: 51px;
					}
				.row-one {
					align-items: center;
					display: flex;
					margin-right: 63px;
					
				}
				.row-two {
					align-items: center;
					display: flex;
				}
			}
			button {
				padding: 22px 0;
				font-weight: 700;
				font-size: 20px;
				line-height: 24px;
				margin-top: 60px;
			}
		}
		.col-two {
			position: relative;
			width: calc(100% / 2);
			.call-pic {
				position: absolute;
				top: 0;
				left: 0;
				transform: translate(6%, -54%);
			}
		}
	}
	/* cov-details END */

	/* get-started START */
	.get-started {
		padding-bottom: 120px;
		.container {
			display: block;
			justify-content: center;
			text-align: center;
		}
		h1 {
			font-weight: 800;
			font-size: 42px;
			line-height: 51px;
		}
		h2 {
			font-weight: 400;
			font-size: 24px;
			line-height: 29px;
			margin: 60px 0 0 0;
		}
		.point {
			display: flex;
			h1 {
				position: absolute;
				top: -50%;
				left: 50%;
				transform: translate(-50%, -33%);
				margin: 0 auto;
				color: rgba(0, 93, 196, 0.11);
				font-weight: 900;
				font-size: 290.244px;
				line-height: 354px;
			}
			.wrapper {
				position: relative;
			}
			.row-one, .row-two {
				.wrapper {
					margin-right: 60px;
				}
			}
			h2 {
				margin: 164px 0 30px;
				font-weight: 700;
				font-size: 24px;
				line-height: 29px;
			}
			p {
				font-weight: 500;
				font-size: 18px;
				line-height: 22px;
			}
		}
		button {
			max-width: 413px;
			margin-top: 50px;
		}
	}
	/* get-started END */

	/* check-qualify START */
	.check-qualify {
		padding-bottom: 120px;
		.container {
			display: block;
			justify-content: center;
			text-align: center;
		}
		h1 {
			font-weight: 800;
			font-size: 42px;
			line-height: 51px;
		}
		h2 {
			display: block;
			max-width: 541px;
			width: 100%;
			margin: 60px auto 30px;
			font-weight: 400;
			font-size: 24px;
			line-height: 29px;
		}
		.point {
			display: grid;
			grid-template-columns: repeat(3, 1fr);
			grid-column-gap: 75px;
			align-items: center;
			img {
				margin-left: auto;
				margin-right: auto;
				margin-bottom: 8px;
			}
			h1 {
				font-weight: 700;
				font-size: 24px;
				line-height: 29px;
				margin-bottom: 20px;
			}
			p {
				font-weight: 500;
				font-size: 18px;
				line-height: 22px;
			}
			.row-one {
				p {
					max-width: 334px;
					width: 100%;
					margin: 0 auto;
				}
			}
			.row-two {
				p {
					max-width: 266px;
					width: 100%;
					margin: 0 auto;
				}
			}
		}
		button {
			max-width: 413px;
			margin-top: 52px;
		}
	}
	/* check-qualify END */

	/* faq START */
	.faq {
		padding-bottom: 120px;
		.column {
			background: #00409F;
			padding: 120px 64px;
			border-radius: 30px;
			color: #FFFFFF;
			h1 {
				font-weight: 800;
				font-size: 42px;
				line-height: 51px;
				text-align: center;
			}
			.point {
				margin: 60px 0 50px;
				display: flex;
				.row-one {
					width: 100%;
					max-width: 498.5px;
					margin-right: 30px;
					li:last-child {
						margin-bottom: 0;
					}
				}
				.row-two {
					width: 100%;
					max-width: 634.54px;
					li:last-child {
						margin-bottom: 0;
					}
				}
				ul {
					font-weight: 700;
					font-size: 22px;
					line-height: 27px;
					li {
						list-style: url();
						margin-bottom: 30px;
					}
				}
				p {
					max-width: 404px;
					width: 100%;
					font-weight: 500;
					font-size: 18px;
					line-height: 22px;
					margin-bottom: 30px;
				}
			}
			button {
				max-width: 413px;
			}
		}
	}
	/* faq END */

	/* map START */
	.map {
		padding-bottom: 120px;
		.map-pic {
			margin-bottom: 100px;
		}
	}
	/* map END */

	/* footer START */
	footer {
		padding: 75px 0 74px;
		background: #01116D;
		.container {
			justify-content: center;
			text-align: center;
		}
		p {
			font-weight: 600;
			font-size: 15px;
			line-height: 135.9%;
			color: #FFFFFF;
		}
	}
	/* footer END */
}
/* #index END */
</style>