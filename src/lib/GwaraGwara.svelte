<script>
    export let goToSlide;
  
    const gwaraGwaraDetails = {
      fact: "Gwara Gwara is a South African dance that gained popularity through the music genre of Afrobeats. The dance involves sweeping and synchronized arm and leg movements that follow the music’s beat. This dance is very energetic and has attention-grabbing moves, making it a favorite in dance challenges and social media.",
      videoUrl: "https://www.tiktok.com/embed/6891617469069413633"
    };
  </script>
  
  <h2>You should try...</h2>
  <h1>Gwara Gwara</h1>
  <p>{gwaraGwaraDetails.fact}</p>
  
  <div class="video-wrapper">
    <iframe
      src={gwaraGwaraDetails.videoUrl}
      title="Gwara Gwara Dance Video"
      allowfullscreen
      allow="autoplay; encrypted-media"
    ></iframe>
  </div>
  
  <button on:click={() => goToSlide(4)}>Back to Map</button>
  
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
  