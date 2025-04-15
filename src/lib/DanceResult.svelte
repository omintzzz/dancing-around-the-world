<script>
  export let goToSlide;
  export let userChoice;

  const danceDetails = {
    "Hip Hop": {
      fact: "Hip hop dance, originating from the Bronx, NY in the early 1970s is characterized by energetic and expressive movements. The style is known for emphasizing freestyle movements and moments of adding personal flair. Some more specific styles of hip hop include popping, which require fluid movements of the arms and legs and body contractions, and locking, which focuses on crisp movements with distinct poses. To dance hip hop successfully, it is important to focus on the music’s rhythm. The music is typically upbeat and fast-paced, which is why the dance style is often associated with high energy.",
      videoUrl: "https://www.tiktok.com/embed/7309474986916465951"
    },
    "Salsa": {
      fact: "Originating in Cuba, salsa dance is known for its energetic footwork, fluid turns, and rhythmic hip movements. This dance style includes a mix of fast and slow steps but is overall very lively. The dance also has body isolations and spins for expressiveness. Salsa is typically danced in pairs, with one partner leading and the other following.",
      videoUrl: "https://www.tiktok.com/embed/7444315228021542174"
    },
    "English Waltz": {
      fact: "The English Waltz is a popular ballroom dance that is seen as smooth, graceful, and elegant. The dance follows a basic box step and includes rotational movements with a partner. This is considered one of the easier waltzes to learn because of the slow, quick, quick pattern that is followed. This dance emphasizes fluidity and maintaining connections with others.",
      videoUrl: "https://www.tiktok.com/embed/7384069865419640096"
    },
    "Samba": {
      fact: "Samba is a lively and rhythmic dance that originates from Brazil. Known for its fast-paced, upbeat music, it involves rhythmic steps and hip movements, often with a sense of bouncing. Samba has evolved into various styles, including ballroom and street samba, with both solo and partner variations.",
      videoUrl: "https://www.tiktok.com/embed/7225182673172483334" 
    },
    "Bhangra": {
      fact: "Bhangra is a lively and energetic folk dance originating from Punjab, India. Traditionally performed during harvest festivals, it has evolved into a popular dance genre worldwide. It is known for its vibrant, rhythmic beats and energetic movements, often involving shoulder shimmying, jumping, and footwork.",
      videoUrl: "https://www.tiktok.com/embed/7213874645108066822" 
    },
    "Gwara Gwara": {
      fact: "Gwara Gwara is a popular dance from South Africa, known for its fluid movements, sharp arm motions, and distinctive footwork. It became internationally recognized after being featured in global music videos. The dance is often performed to Afrobeat and house music.",
      videoUrl: "https://www.tiktok.com/embed/7213874645108066822" 
    }
  };
</script>

{#if danceDetails[userChoice]}
  <h2>You should try...</h2>
  <h1>{userChoice}</h1>
  <p>{danceDetails[userChoice].fact}</p>

  <div class="video-wrapper">
    <iframe
      src={danceDetails[userChoice].videoUrl}
      title="Dance video for {userChoice}"
      allowfullscreen
      allow="autoplay; encrypted-media"
    ></iframe>
  </div>
{:else}
  <p>No information found for that dance style.</p>
{/if}

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
