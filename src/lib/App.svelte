<script>
	// @<script>
  import Homepage from './Homepage.svelte';
  import QuizComponent from './QuizComponent.svelte';
  import DanceResult from './DanceResult.svelte';
  import MapComponent from './MapComponent.svelte';
  import Samba from './Samba.svelte';
  import GwaraGwara from './GwaraGwara.svelte';
  import Bhangra from './Bhangra.svelte';

  let currentSlide = 1;
  let userChoice = "";

  const goToSlide = (n) => {
    currentSlide = n;
  };

  const updateChoice = (choice) => {
    userChoice = choice;
  };
</script>

{#if currentSlide === 1}
  <Homepage goToSlide={goToSlide} />
{:else if currentSlide === 2}
  <QuizComponent goToSlide={goToSlide} updateChoice={updateChoice} />
{:else if currentSlide === 3}
  <DanceResult goToSlide={goToSlide} userChoice={userChoice} />
{:else if currentSlide === 4}
  <MapComponent goToSlide={goToSlide} updateChoice={updateChoice} />
{:else if currentSlide === 5}
  <Samba goToSlide={goToSlide} />
{:else if currentSlide === 6}
  <GwaraGwara goToSlide={goToSlide} />
{:else if currentSlide === 7}
  <Bhangra goToSlide={goToSlide} />
{/if}

<style>
    :global(body) {
    background: linear-gradient(135deg, #FE2C55, #25F4EE);
    margin: 0;
    padding: 0;
    font-family: 'Roboto', sans-serif;
  }
</style>