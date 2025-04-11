<script>
  export let goToSlide;
  export let updateChoice;
</script>

<div id="map">
  <h3>Map of Dance Locations</h3>
  <p><strong>Click a region to explore its dance style!</strong></p>

  <img
    src="https://www.worldometers.info/world-map/world-map.jpg"
    width="700"
    height="500"
    usemap="#workmap"
    alt="World Map"
  />

  <map name="workmap">
    <!-- Hip Hop: Bronx, NYC -->
    <area
      shape="circle"
      coords="315,313,15"
      alt="Hip Hop"
      role="button"
      tabindex="0"
      on:click|preventDefault={(e) => {
        updateChoice("Hip Hop");
        goToSlide(3);
      }}
      on:keydown={(e) => {
        if (e.key === 'Enter') {
          updateChoice("Hip Hop");
          goToSlide(3);
        }
      }}
    />

    <area
      shape="circle"
      coords="297,388,15"
      alt="Salsa"
      role="button"
      tabindex="0"
      on:click|preventDefault={(e) => {
        updateChoice("Salsa");
        goToSlide(3);
      }}
      on:keydown={(e) => {
        if (e.key === 'Enter') {
          updateChoice("Salsa");
          goToSlide(3);
        }
      }}
    />
    />

    <area
      shape="circle"
      coords="609,285,15"
      alt="Viennese Waltz"
      role="button"
      tabindex="0"
      on:click|preventDefault={(e) => {
        updateChoice("Viennese Waltz");
        goToSlide(3);
      }}
      on:keydown={(e) => {
        if (e.key === 'Enter') {
          updateChoice("Viennese Waltz");
          goToSlide(3);
        }
      }}
    />
      }}
    />

  <button on:click={() => goToSlide(2)}>Back to Quiz</button>
</div>

<style>
  #map {
    text-align: center;
    margin-top: 2rem;
  }

  img {
    border: 2px solid #ccc;
    border-radius: 8px;
  }

  area:hover {
    cursor: pointer;
  }

  area:focus {
    outline: 2px solid #ff6347; /* Change focus outline color to make it stand out */
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
</style>
