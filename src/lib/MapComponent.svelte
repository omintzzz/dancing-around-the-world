<script>
  import { onMount } from "svelte";
  import mapboxgl from "mapbox-gl";
  import "mapbox-gl/dist/mapbox-gl.css"; // ✅ Import Mapbox CSS

  export let goToSlide;
  export let updateChoice;

  mapboxgl.accessToken = "pk.eyJ1Ijoib21pbnR6enoiLCJhIjoiY204eW5ocnN0MDBmeDJrb2FzeHA0ODNvZyJ9.QMAL3XlhRCYHf-Xywn6FhA";

  let map;

  const danceLocations = [
    {
      name: "Hip Hop",
      coords: [-73.92357, 40.82732],
      type: "quiz",
      popupContent: "Hip Hop - Bronx, NY"
    },
    {
      name: "Salsa",
      coords: [-75.82667, 20.02083],
      type: "quiz",
      popupContent: "Salsa - Santiago de Cuba"
    },
    {
      name: "English Waltz",
      coords: [-0.1278, 51.5074],
      type: "quiz",
      popupContent: "English Waltz - London"
    },
    {
      name: "Samba",
      coords: [-51.9253, -14.2350],
      type: "extra",
      slide: 5,
      popupContent: "Samba - Brazil"
    },
    {
      name: "Gwara Gwara",
      coords: [22.9375, -30.5595],
      type: "extra",
      slide: 6,
      popupContent: "Gwara Gwara - South Africa"
    },
    {
      name: "Bhangra",
      coords: [75.8577, 31.1048],
      type: "extra",
      slide: 7,
      popupContent: "Bhangra - Punjab, India"
    },
  ];

  function handleClick(dance) {
    if (dance.type === "quiz") {
      updateChoice(dance.name);
      goToSlide(3);
    } else if (dance.type === "extra" && dance.slide) {
      goToSlide(dance.slide);
    }
  }

  onMount(() => {
    map = new mapboxgl.Map({
      container: "map",
      style: "mapbox://styles/mapbox/light-v10",
      center: [0, 20],
      zoom: 1,
    });

    map.scrollZoom.disable();
    map.boxZoom.disable();
    map.dragRotate.disable();
    map.dragPan.disable();
    map.keyboard.disable();
    map.doubleClickZoom.disable();
    map.touchZoomRotate.disable();

    danceLocations.forEach((dance) => {
      const el = document.createElement("div");
      el.setAttribute("class", "marker");
      el.setAttribute("title", dance.popupContent);

      el.addEventListener("click", () => handleClick(dance));

      const marker = new mapboxgl.Marker(el)
        .setLngLat(dance.coords)
        .addTo(map);

      const popup = new mapboxgl.Popup({ offset: 25 })
        .setText(dance.popupContent);

      marker.setPopup(popup);
    });
  });
</script>

<div id="map-container">
  <h2><strong>Choose a circle to learn about a new dance!</strong></h2>
  <div id="map"></div>
  <button on:click={() => goToSlide(2)}>Take the Quiz Again</button>
</div>

<style>
  #map-container {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    min-height: 100vh;
    text-align: center;
    padding: 2rem;
  }

  h2{
    margin: 0.5rem 0;
    font-family: 'Poppins', sans-serif;
  }

  #map {
    width: 1000px;
    height: 700px;
    margin: 1rem 0;
    border-radius: 8px;
  }

  :global(.marker) {
    width: 20px;
    height: 20px;
    background-color: #FE2C55;
    border-radius: 50%;
    cursor: pointer;
    border: 2px solid white;
    box-shadow: 0 0 5px rgba(0, 0, 0, 0.3);
    /* ✅ removed position: relative and z-index */
  }

  :global(.marker):hover {
    transform: scale(1.3);
    transition: transform 0.2s;
  }

  button {
    margin-top: 1.5rem;
    padding: 0.5rem 1rem;
    background-color: #FE2C55;
    color: white;
    border: none;
    border-radius: 8px;
    font-size: 1rem;
    cursor: pointer;
  }

  button:hover {
    background-color: #666;
  }
</style>
