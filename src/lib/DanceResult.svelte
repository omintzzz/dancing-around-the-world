<script>
    export let goToSlide;
    export let userChoice;
  
    const danceDetails = {
      "Hip Hop": {
        fact: "Hip hop dance is a collection of street dance styles including breaking, locking, and popping. Many of these styles originated in The Bronx, NY.",
        videoUrl: "https://www.youtube.com/embed/5D5jV5Q5JrM"
      },
      "Viennese Waltz": {
        fact: "The Viennese waltz originated in Austria and is known for its smooth, flowing movements.",
        videoUrl: "https://www.youtube.com/embed/5D5jV5Q5JrM"
      },
      "Salsa": {
        fact: "Salsa is a popular dance style that originated in Cuba and has evolved to include various international influences.",
        videoUrl: "https://www.youtube.com/embed/5D5jV5Q5JrM"
      }
    };
  </script>
  
  {#if danceDetails[userChoice]}
    <h2>Your Result: {userChoice}</h2>
    <p>{danceDetails[userChoice].fact}</p>
    <!-- svelte-ignore a11y_missing_attribute -->
    <iframe
      src={danceDetails[userChoice].videoUrl}
      width="560"
      height="315"
      frameborder="0"
      allowfullscreen
    ></iframe>
  {:else}
    <p>Oops! We couldn't find information for your choice.</p>
  {/if}
  
  <button on:click={() => goToSlide(4)}>Go to Map</button>
  
  <style>
  h2 {
    margin-top: 1rem;
  }
  iframe {
    margin: 1rem 0;
    border-radius: 8px;
  }
  button {
    padding: 0.5rem 1rem;
    font-size: 1rem;
    background-color: #222;
    color: white;
    border: none;
    border-radius: 5px;
    cursor: pointer;
  }
  button:hover {
    background-color: #444;
  }
  </style>
  