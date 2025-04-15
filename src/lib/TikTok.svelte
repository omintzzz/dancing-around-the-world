<script>
  import { onMount } from 'svelte';
  export let videoId;

  onMount(() => {
    const existingScript = document.querySelector('script[src="https://www.tiktok.com/embed.js"]');
    if (!existingScript) {
      const script = document.createElement('script');
      script.setAttribute('src', 'https://www.tiktok.com/embed.js');
      script.setAttribute('async', '');
      document.body.appendChild(script);
    } else {
      if (window.tiktokEmbedLoad) {
        window.tiktokEmbedLoad();
      }
    }
  });
</script>

<style>
  .embed-wrapper {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    padding: 1rem;
  }
</style>

<div class="embed-wrapper">
  <blockquote
    class="tiktok-embed"
    cite={`https://www.tiktok.com/@placeholder/video/${videoId}`}
    data-video-id={videoId}
    style="max-width: 605px; min-width: 325px;"
  >
    <section>Loading TikTok video...</section>
  </blockquote>
</div>
