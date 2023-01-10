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
					<FreePhone class="phone-pic"/>
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
							<svg width="31" height="51" viewBox="0 0 31 51" fill="none" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink">
								<mask id="mask0_771_488" style="mask-type:alpha" maskUnits="userSpaceOnUse" x="0" y="0" width="31" height="51">
								<rect width="30.4756" height="51" fill="url(#pattern0)"/>
								</mask>
								<g mask="url(#mask0_771_488)">
								<rect x="-3.10938" y="-3.73169" width="35.4512" height="55.3537" fill="#005DC4"/>
								</g>
								<defs>
								<pattern id="pattern0" patternContentUnits="objectBoundingBox" width="1" height="1">
								<use xlink:href="#image0_771_488" transform="scale(0.0204082 0.0121951)"/>
								</pattern>
								<image id="image0_771_488" width="49" height="82" xlink:href="data:image/png;base64,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"/>
								</defs>
							</svg>
							<p>FREE 25GB of High-
								Speed Data AND UP TO 5GB
								of Hotspot Data**
								Compatible device required.</p>
						</div>
						<div class="row-two">
							<svg width="47" height="51" viewBox="0 0 47 51" fill="none" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink">
								<mask id="mask0_771_485" style="mask-type:alpha" maskUnits="userSpaceOnUse" x="0" y="0" width="47" height="51">
								<rect width="46.92" height="51" fill="url(#pattern0)"/>
								</mask>
								<g mask="url(#mask0_771_485)">
								<rect width="48.45" height="53.04" fill="#005DC4"/>
								</g>
								<defs>
								<pattern id="pattern0" patternContentUnits="objectBoundingBox" width="1" height="1">
								<use xlink:href="#image0_771_485" transform="scale(0.0108696 0.01)"/>
								</pattern>
								<image id="image0_771_485" width="92" height="100" xlink:href="data:image/png;base64,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"/>
								</defs>
							</svg>
							<p>Unlimited Talk & Text + Calls
								to Canada & Mexico* + FREE
								Smartphone or SIM Card
								Most GSM Smartphones are compatible.</p>
						</div>
					</div>
					<button>GET FREE UNLIMITED TALK &TEXT + DATA EVERY MONTH >></button>
				</div>
				<div class="col-two">
					<CoverageDetails class="call-pic"/>
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
						<!-- do a bg-img in row -->
						<div class="row-one">
							<h1>CONFIRM ELIGIBILITY</h1>
							<p>Confirm if anyone in your household participates in a qualifying program.</p>
						</div>
						<div class="row-two">
							<h1>APPLY FOR ACP</h1>
							<p>Provide the necessary information or fill out your application.</p>
						</div>
						<div class="row-three">
							<h1>ENJOY YOUR SERVICE</h1>
							<p>Receive a notification of your approval within 48 hours.</p>
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
					<!-- add an img in row -->
					<div class="point">
						<div class="row-one">
							<img src="#">
							<h1>GOVERNMENT ASSISTANCE</h1>
							<p>You participate in certain assistance programs
								such as SNAP, Medicaid, or LifeLine.</p>
						</div>
						<div class="row-two">
							<img src="#">
							<h1>RECEIVED A PELL GRANT</h1>
							<p>You received a Federal Pell Grant during the current award year.</p>
						</div>
						<div class="row-three">
							<img src="#">
							<h1>LUNCH PROGRAMS</h1>
							<p>You received approval for benefits under the free
								and reduced-price school lunch program.</p>
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
					<p>Video typically streams at DVD quality.
						*Dial up to 15 unique landline and mobile numbers
						(in select destinations only, which are subject to change at any time)
						each 30-day cycle. Calls must originate from the US or Puerto Rico;
						no international roaming allowed. **Your Hotspot or BYOP service
						can only be activated where Service is available, offered, and supported.
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
@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@500;700;800&display=swap');

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
						font-size: 12px;
						margin: auto 0;
				}
			}
			button {
				max-width: 413px;
				justify-content: start;
				margin: 46px 0 30px;
			}
			p {
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
				transform: translate(12%, -39%);
			}
		}
	}
	/* free-smartphone END */

	/* cov-details START */
	.cov-details {
		padding: 67px 0 74px;
		.container {
			display: flex;
			justify-content: center;
			align-items: center;
		}
		.col-one {
			width: 703px;
			h1 {
				font-weight: 800;
				font-size: 42px;
				line-height: 51px;
			}
			h2 {
				font-weight: 400;
				font-size: 24px;
				line-height: 29px;
				margin: 60px 0 40px;
			}
			.point {
				display: flex;
				.row-one {
					display: flex;
					margin-right: 77px;
					p {
						max-width: 257px;
						width: 100%;
						font-weight: 400;
						font-size: 18px;
						line-height: 22px;
						margin-left: 15px;
					}
				}
				.row-two {
					display: flex;
					p {
						max-width: 257px;
						width: 100%;
						font-weight: 400;
						font-size: 18px;
						line-height: 22px;
						margin-left: 15px;
					}
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
				transform: translate(10%, -40%);
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
			margin: 60px 0 30px;
		}
		.point {
			display: flex;
			h1 {
				font-weight: 700;
				font-size: 24px;
				line-height: 29px;
			}
			p {
				font-weight: 500;
				font-size: 18px;
				line-height: 22px;
			}
			.row-one {
				margin-right: 112px;
			}
			.row-two {
				margin-right: 112px;
			}
			.rwo-three {
				background-image: url(#);
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
			font-weight: 400;
			font-size: 24px;
			line-height: 29px;
			margin: 60px 0 30px;
		}
		.point {
			display: flex;
			img {
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
				margin-right: 112px;
			}
			.row-two {
				margin-right: 112px;
			}
			.rwo-three {
				background-image: url(#);
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
					font-size: 24px;
					line-height: 29px;
					li {
						margin-bottom: 30px;
					}
				}
				p {
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
			font-size: 16px;
			line-height: 135.9%;
			color: #FFFFFF;
		}
	}
	/* footer END */
}
/* #index END */
</style>