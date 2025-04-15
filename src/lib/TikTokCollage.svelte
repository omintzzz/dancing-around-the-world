<script>
	export let videos;
  </script>
  
  <div class="video-container">
	{#each videos as video}
	  <video src={video} controls>
		<track kind="captions" src="path/to/captions.vtt" srclang="en" label="English" default>
	  </video>
	{/each}
  </div>
  
  <style>
	.video-container {
	  display: flex;
	  justify-content: center;
	  align-items: center;
	  gap: 1rem;
	  flex-wrap: wrap;
	  width: 100%;
	}
  
	video {
	  max-width: 100%;
	  height: auto;
	  border-radius: 8px;
	}
  </style>
  