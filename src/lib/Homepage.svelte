<script>
// @ts-nocheck

	import Scrolly from "./Scrolly.svelte";
	import QuizComponent from "./QuizComponent.svelte";
	import TikTokCollage from "./TikTokCollage.svelte";
  
	export let goToSlide;
  
	let value;
  
	const steps = [
	  "<p> Dance is universal, but TikTok has made it even easier. Whether it be sharing cultural dance styles or circulating some trendy moves to a popular song, this app has been a key component in making dance more accessible for people all over the world. </p>",
    "<p> The short-form video platform know for spreading knowledge and culture has seen an increase in showcasing various dance styles around the world. Especially in the digital age, there has been a shift in how people dance and how it is viewed in general. </p>",
    "<p> Though the app was never made specifically for dance, the app initially was known for its contribution to creating dance challenges that users could replicate with their own style. These challenges were not extremely complicated but typically included arm and upper body movements. Dances like the Renegade, Say So, and Supalonely became popular online during the pandemic as many people were home. </p>",
	"<p> Another paragraph about sharing different dances that are not tik tok specific... </p>",
    "<p> Take this quiz to see what dance style would suit you the best </p>"
	];
  
	const videos = [  
	  "https://www.tiktok.com/@aimerskidsfoundation/video/7227898562791722246",
	  "https://www.tiktok.com/@mondayswithmohan/video/7456117497104747806",
	  "https://www.tiktok.com/@dabke_aus/video/7337663555900099842",
	  "https://www.tiktok.com/@fenua.dp/video/7117669442749811973",
	  "https://www.tiktok.com/@nativeamericancultures/video/7462188915118607659",
	  "https://www.tiktok.com/@arwenmatthijssen/video/7419790391274229024",
	  "https://www.tiktok.com/@lukaaleksandria__/video/7209239439162215682",
	  "https://www.tiktok.com/@josevalenciaofficial/video/7444315228021542174",
	  "https://www.tiktok.com/@chrisjordanwilks/video/7309474986916465951",
	  "https://www.tiktok.com/@_cairde/video/7344048902372363562",
	  "https://www.tiktok.com/@balletblogx/video/7314409238175026465",
	  "https://www.tiktok.com/@hbcuitgirls/video/7438451282962042143"
	];
  </script>
  
  <div class="container">
	<div class="background">
	  <div class="overlay"></div>
	</div>
  
	<section>
	  <div class="hero">
		<h1>Dancing Around the World!</h1>
		<h3>By Olivia Mintz</h3>
	  </div>
  
	  <div class="section-container">
		<div class="steps-container">
		  <Scrolly bind:value>
			{#each steps as text, i}
			  <div class="step" class:active={value === i}>
				<div class="step-content">{@html text}</div>
			  </div>
			{/each}
			<!-- svelte-ignore element_invalid_self_closing_tag -->
			<div class="spacer" />
		  </Scrolly>
		</div>
  
		<div class="sticky"></div>
	  </div>
  
	  <div class="tiktok-container">
		<TikTokCollage videos={videos} />
	  </div>
	</section>
  
	<button on:click={() => goToSlide(2)}>Go to Quiz</button>
  </div>
  
  <style>
	.container {
	  position: relative;
	  width: 100%;
	  overflow: hidden;
	}
  
	.background {
	  position: fixed;
	  top: 0;
	  left: 0;
	  width: 100%;
	  height: 100vh;
	  z-index: 0;
	  overflow: hidden;
	  pointer-events: none;
	}
  
	.overlay {
	  position: absolute;
	  inset: 0;
	  background: rgba(0, 0, 0, 0.4);
	  z-index: 1;
	}
  
	section {
	  position: relative;
	  z-index: 2;
	  color: white;
	}
  
	.hero {
	  height: 60vh;
	  display: flex;
	  place-items: center;
	  flex-direction: column;
	  justify-content: center;
	  text-align: center;
	}
  
	.section-container {
	  display: flex;
	  margin-top: 1em;
	}
  
	.steps-container {
	  flex: 1 1 40%;
	  z-index: 2;
	}
  
	.sticky {
	  position: sticky;
	  top: 10%;
	  flex: 1 1 60%;
	  width: 60%;
	}
  
	.step {
	  height: 80vh;
	  display: flex;
	  place-items: center;
	  justify-content: center;
	}
  
	.step-content {
	  background: rgba(255, 255, 255, 0.85);
	  color: black;
	  border-radius: 5px;
	  padding: 1rem;
	  max-width: 500px;
	  margin: auto;
	  box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
	}
  
	.spacer {
	  height: 40vh;
	}
  
	.step.active .step-content {
	  background: white;
	  color: black;
	}
  
	.tiktok-container {
	  padding-top: 2rem;
	  text-align: center;
	}
  
	button {
	  margin-top: 1.5rem;
	  padding: 0.5rem 1rem;
	  border-radius: 8px;
	  background-color: #444;
	  color: white;
	  border: none;
	  font-size: 1rem;
	  cursor: pointer;
	}
  
	button:hover {
	  background-color: #666;
	}
  
	@media screen and (max-width: 768px) {
	  .section-container {
		flex-direction: column-reverse;
	  }
  
	  .sticky {
		width: 95%;
		margin: auto;
	  }
	}
  </style>
  