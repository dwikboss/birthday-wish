<template>
	<div class="letter">
		<div class="text">
			<span style="font-size: 1.8rem;">Gefeliciteerd met je (bijna) 22ste verjaardag Anouk!!! 😁😁</span><br/><br/>
			Sinds de dag dat we vrienden zijn geworden hebben we al zo veel leuke dingen meegemaakt en gedaan en zo veel coole memories gemaakt!!
			Van K-Pop tot Glee van CINEMA 😎 tot concerten hebben we 1001 dingen om te doen en over te praten! Het is zo zo zo zo zo leuk dat we al die dingen samen kunnen doen en ik hoop dat daar 1000000 dingen bij gaan komen zzzz.
			Van alle nieuwe dingen die in mijn leven zijn gekomen ben jij zeker S+++ tier!! Dus ik zou zeggen, geniet van deze top dag!!! 🛂😁😎🛂
		</div>
	</div>
</template>

<script>
export default {
	name: 'LetterComponent',
	props: {
	},
	data() {
		return {
		};
	},
	methods: {
		
	},
}
</script>

<style scoped lang="scss">
    .letter {
		padding: 30px;
        position: absolute;
        width: 85vw;
        border: 3px solid black;
        background-color: white;
		top: -80vh;
		left: 50%;
		-webkit-transform: translateX(-50%);
		transform: translateX(-50%) rotate(2deg);
		z-index: 999;
		color: black;
		text-align: left;
		animation: slideDown 800ms ease-in-out 1.5s forwards;

		.text {
			font-size: 1.4rem;
		}
    }
	
	@keyframes slideDown {
		0% {
			top: -80vh;
		}
		100% {
			top: 5vh;
		}
	}
</style>
