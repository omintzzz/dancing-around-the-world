<script>
    export let goToSlide;
  
    const sambaDetails = {
      fact: "Samba is a lively and rhythmical dance that originated in Brazil. It's a national symbol of Brazil and is often performed during Carnival. Samba involves quick footwork, rhythmic body movements, and is usually accompanied by vibrant, festive music. The dance also emphasizes bounce movements due to rapid bending and straightening of the knees along with rolling hip and pelvic movements.",
      videoUrl: "https://www.tiktok.com/embed/7340439192645782827"
    };
  </script>
  
  <h2>You should try...</h2>
  <h1>Samba</h1>
  <p>{sambaDetails.fact}</p>
  
  <div class="video-wrapper">
    <iframe
      src={sambaDetails.videoUrl}
      title="Samba Dance Video"
      allowfullscreen
      allow="autoplay; encrypted-media"
    ></iframe>
  </div>
  
  <button on:click={() => goToSlide(4)}>Go to Map</button>
  
  <style>
    h2 {
      margin-top: 1rem;
      text-align: center;
    }
  
    p {
      max-width: 600px;
      margin: 1rem auto;
      line-height: 1.6;
      text-align: center;
    }
  
    .video-wrapper {
      width: 100%;
      max-width: 400px;
      margin: 1.5rem auto;
      border-radius: 8px;
      overflow: hidden;
    }
  
    iframe {
    height: 800px; /* Tall enough to avoid TikTok scrollbar */
    border: none;
    clip-path: inset(0px 0px 80px 0px);
  }
  
    button {
      display: block;
      margin: 2rem auto;
      padding: 0.5rem 1rem;
      font-size: 1rem;
      background-color: #FE2C55;
      color: white;
      border: none;
      border-radius: 5px;
      cursor: pointer;
    }
  
    button:hover {
      background-color: #444;
    }
  </style>
  