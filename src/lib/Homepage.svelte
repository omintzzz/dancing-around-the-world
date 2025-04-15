<script>
	import QuizComponent from "./QuizComponent.svelte";
	import TikTok from './TikTok.svelte';
	export let goToSlide;
</script>

<!-- Video Background -->
<div class="video-background">
	<video autoplay muted loop playsinline>
		<source src="/videos/61efbfeab5b42dd347f2f0aa616d1de7.mp4" type="video/mp4" />
		Your browser does not support the video tag.
	</video>
</div>

<!-- Main Content -->
<div class="container">
	<div class="background">
		<div class="overlay"></div>
	</div>

	<section>
		<!-- TikTok Embed that scrolls with content -->
		<div class="tiktok-wrapper">
			<TikTok videoId="7483601648313486647" />
		</div>

		<div class="hero">
			<h1>Dancing Around the World!</h1>
			<h3>By Olivia Mintz</h3>
		</div>

		<div class="narrative-text">
			<p> Dance is universal, but TikTok has made it even easier to see. Whether it be sharing cultural dance styles or circulating trendy moves to a popular song, this app has been a key component in making dance more accessible for people all over the world.</p>
			<p> The short-form video platform known for spreading knowledge and influencing pop culture has seen an increase in showcasing various dance styles around the world. Especially in the digital age, there has been a shift in how people dance and how it is viewed in general. </p>
			<p> Originally known as Musical.ly, TikTok has undergone many iterations of its content and goals. Musical.ly was most notably used for lip syncing videos. After being bought by ByteDance, in 2018, it donned the name TikTok and was known as “the dance app”. </p>
			<p>The app’s format helped users contribute to creating dance challenges that others could replicate with their own personal touch. These challenges were not choreographed to be complicated as they typically included arm and upper body movements. Dances like the Renegade, Say So, and Supalonely became popular online during the pandemic as many people were home. In addition to having viral dance moments, TikTok fosters a community for those involved in the industry to share their choreography and include more advanced challenges to the app. </p>
			<p> Though much of the viral dance content comes from the United States, users from other countries tend to put their own spin on choreography and utilize songs that may not be in English. </p>

			<p> Take this quiz to learn about a new dance style and see which one fits you the best.</p>
		</div>
	</section>

	<button on:click={() => goToSlide(2)}>
		Take the quiz!
	</button>
</div>

<style>
	@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@400;600&display=swap');

	* {
		font-family: 'Poppins', sans-serif;
		box-sizing: border-box;
	}

	.video-background {
		position: fixed;
		top: 0;
		left: 0;
		width: 100%;
		height: 100vh;
		z-index: -1;
		overflow: hidden;
	}

	.video-background video {
		width: 100%;
		height: 100%;
		object-fit: cover;
	}

	.container {
		position: relative;
		width: 100%;
		overflow: hidden;
		color: white;
	}

	.background {
		position: fixed;
		top: 0;
		left: 0;
		width: 100%;
		height: 100vh;
		z-index: 0;
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

	.tiktok-wrapper {
		margin: 2rem auto;
		max-width: 325px;
		aspect-ratio: 9 / 16;
		border-radius: 12px;
		overflow: hidden;
	}

	.hero {
		position: relative;
		height: 60vh;
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		text-align: center;
		overflow: hidden;
	}

	.hero h3 {
		margin-bottom: 0.5rem;
	}

	.narrative-text {
		padding: 2rem;
		max-width: 800px;
		margin: 0 auto;
		font-size: 1.2rem;
		line-height: 1.6;
		text-align: left;
		margin-top: 0;
	}

	button {
		margin-top: 1.5rem;
		padding: 0.5rem 1rem;
		border-radius: 8px;
		background-color: #EE1D52;
		color: white;
		border: none;
		font-size: 1rem;
		cursor: pointer;
		transition: background-color 0.3s ease;
	}

	button:hover {
		background-color: #c41745;
	}
</style>
