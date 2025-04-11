<script>
// @ts-nocheck

	import Homepage from "./Homepage.svelte";
	import QuizComponent from "./QuizComponent.svelte";
	import DanceResult from "./DanceResult.svelte";
	import MapComponent from "./MapComponent.svelte";
  
	let currentSlide = 1;
	let userChoice = "";
  
	function goToSlide(slideNum) {
	  currentSlide = slideNum;
	}
  
	function updateChoice(newChoice) {
	  userChoice = newChoice;
	}
  </script>
  
  {#if currentSlide === 1}
	<Homepage {goToSlide} />
  {:else if currentSlide === 2}
	<QuizComponent {goToSlide} {updateChoice} />
  {:else if currentSlide === 3}
	<DanceResult {goToSlide} {userChoice} />
  {:else if currentSlide === 4}
	<MapComponent {goToSlide} />
  {/if}
  
  