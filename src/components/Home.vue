<template>
	<div class="screen">
		<h1>{{ candles.length }}</h1>
		<img class="cake-img" src="@/assets/cake.png" @click="dropCandle"/>
		<svg version="1.1" v-for="(candle, index) in candles"  :style="{ left: candle.position.left + 'px', transform: 'rotate(' + candle.rotation + 'deg)' }" :key="index" class="candle falling" :ref="'candle' + index" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" x="0px" y="0px" viewBox="0 0 41.4 199.7" style="enable-background:new 0 0 41.4 199.7;" xml:space="preserve">
		<g>
			<rect x="4" y="52.6" :style="{ fill: candle.color, rotate: candle.rotation, stroke: '#000000', strokeWidth: 8, strokeMiterlimit: 10 }" width="33.4" height="143.1" />
			<line style="fill:#F8ED3E;stroke:#000000;stroke-width:3;stroke-miterlimit:10;" x1="37.4" y1="82.1" x2="4" y2="95.1"/>
			<line style="fill:#F8ED3E;stroke:#000000;stroke-width:3;stroke-miterlimit:10;" x1="37.4" y1="113.9" x2="4" y2="126.9"/>
			<line style="fill:#F8ED3E;stroke:#000000;stroke-width:3;stroke-miterlimit:10;" x1="37.4" y1="145.6" x2="4" y2="158.6"/>
		</g>
		<line style="fill:#F8ED3E;stroke:#000000;stroke-width:2;stroke-miterlimit:10;" x1="20.7" y1="51.5" x2="20.7" y2="28"/>
		<path class="flame" style="fill:#F78F28;stroke:#000000;stroke-width:2;stroke-miterlimit:10;" d="M17.8,33.4c0,0,6.9,1.6,9.5-2.6
			s4.1-9.8-1.5-17.7S19.1,0.3,19.1,0.3s3.2,11.8-3.8,16.7S13,31.8,17.8,33.4z"/>
		</svg>
	</div>
</template>

<script>
export default {
	name: 'HelloWorld',
	props: {
	},
	data() {
		return {
			candles: [],
			candleColors: ['#F8ED3E', '#E575AE', '#70CFEE', '#BFDEA2', '#F74141', '#FF66FB', '#9C70FC'],
		};
	},
	methods: {
		dropCandle(event) {
			const mouseX = event.clientX;
			const newCandle = {
				id: Date.now(),
				position: { left: mouseX - 10},
				color: this.getRandomColor(),
				rotation: this.getRandomRotation(),
			};
			this.candles.push(newCandle);
			console.log(mouseX);
		},
		getRandomColor() {
			const randomIndex = Math.floor(Math.random() * this.candleColors.length);
			return this.candleColors[randomIndex];
		},
		getRandomRotation() {
			return Math.floor(Math.random() * 30) - 15;
		},
		getRandomDeepness() {
			return Math.random() * (370 - 360) + 360;
		},
		
	},
}
</script>

<style scoped lang="scss">
.screen {
	width: 100vw;
	height: 100vh;
	background: rgb(249,226,254);
	background: linear-gradient(0deg, rgba(249,226,254,1) 0%, rgba(203,153,249,1) 100%);
	padding: 10% 0 0 0;
	overflow: hidden;

	h1 {
		font-size: 30rem;
		color: #0000004b;
		height: 25%;
		position: absolute;
		left: 50%;
		-webkit-transform: translateX(-50%);
		transform: translateX(-50%);
	}

	img, svg {
		max-width: 100%;
	}

	.cake-img {
		margin-top: 0px;
		width: 320px;
		position: absolute;
		left: 50%;
		-webkit-transform: translateX(-50%);
		transform: translateX(-50%);
		top: 450px;
		z-index: 999;
	}

	.candle {
		position: absolute;
		width: 20px;
		left: 0;

		.flame {
			animation: swayAnimation 300ms ease-in-out infinite;
		}
	}

	.falling {
		animation: fallAnimation 400ms cubic-bezier(0.82, 0.4, 0.55, 1.25) forwards;
	}

	@keyframes fallAnimation {
		0% {
			top: 0px;
		}
		100% {
			top: 360px;
		}
	}

	@keyframes swayAnimation {
		0% {
			transform: rotate(-2deg);
		}
		50% {
			transform: rotate(2deg);
		}
		100% {
			transform: rotate(-2deg);
		}
	}
}
</style>
