<script>
	export let tiktoks = [];
</script>

<div class ="collage">
	{#each tiktoks as url}
	<!-- svelte-ignore a11y_missing_attribute -->
	<iframe
		src={url.replace("/video/", "/embed/")}
		frameborder="0"
		allowfullscreen
		class="tiktok-frame"
		></iframe>
	{/each}
</div>

<style>
	.collage {
		display: grid;
		grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
		gap: 1rem;
		padding: 2rem;
		width: 100%;
	}

	.tiktok-frame {
		width: 100%;
		height: 500px;
		border-radius: 10px;
	}
</style>