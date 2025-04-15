<script>
    export let goToSlide;
  
    const bhangraDetails = {
      fact: "Bhangra is a lively form of dance that originated in the Punjab region of India and Pakistan. It is characterized by energetic movements, vibrant music, and colorful attire. Traditionally performed during harvest festivals, Bhangra has evolved into a popular dance form worldwide, often seen at weddings and cultural celebrations. The dance involves rhythmic footwork, shoulder shimmies, and sweeping arm movements, making it a joyful expression of celebration and community.",
      videoUrl: "https://www.tiktok.com/embed/7491800717897010478"
    };
  </script>
  
  <h2>You should try...</h2>
  <h1>Bhangra</h1>
  <p>{bhangraDetails.fact}</p>
  
  <div class="video-wrapper">
    <iframe
      src={bhangraDetails.videoUrl}
      title="Bhangra Dance Video"
      allowfullscreen
      allow="autoplay; encrypted-media"
    ></iframe>
  </div>
  
  <button on:click={() => goToSlide(4)}>Check out More Dances</button>
  
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
  