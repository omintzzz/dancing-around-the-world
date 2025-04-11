<script>
  export let goToSlide;
  export let updateChoice;

  let questions = [
    {
      text: "How would you describe the type of music you listen to?",
      options: [
        { text: "Upbeat and energetic", result: "Hip Hop" },
        { text: "Slow and smooth", result: "Viennese Waltz" },
        { text: "A mix of the two", result: "Salsa" }
      ],
      selected: null
    },
    {
      text: "Do you prefer more intricate or freeform movements?",
      options: [
        { text: "Freeform", result: "Hip Hop" },
        { text: "Intricate", result: "Viennese Waltz" },
        { text: "A little bit of both", result: "Salsa" }
      ],
      selected: null
    },
    {
      text: "Are you a fast learner?",
      options: [
        { text: "Yes", result: "Salsa" },
        { text: "No", result: "Viennese Waltz" },
        { text: "Somewhat", result: "Hip Hop" }
      ],
      selected: null
    }
  ];

  let submitted = false;
  let result = "";

  function submitQuiz() {
    submitted = true;

    // Count occurrences of each result type
    let counts = { "Hip Hop": 0, "Viennese Waltz": 0, "Salsa": 0 };

    for (let question of questions) {
      if (question.selected) {
        counts[question.selected.result]++;
      }
    }

    // Determine the most selected type
    let maxCount = Math.max(...Object.values(counts));
    result = Object.keys(counts).find(type => counts[type] === maxCount);

    updateChoice(result); // Pass result to parent
    goToSlide(3); // Move to the results page
  }
</script>

<main>
  {#each questions as question}
    <div class="question">
      <p>{question.text}</p>
      {#each question.options as option}
        <label>
          <input type="radio" bind:group={question.selected} value={option} />
          {option.text}
        </label>
      {/each}
    </div>
  {/each}

  <button on:click={submitQuiz}>Submit</button>

  {#if submitted}
    <div class="results">
      <h2>Your Result: {result}</h2>
    </div>
  {/if}
</main>

<style>
  .question {
    margin-bottom: 20px;
  }
  .results {
    margin-top: 20px;
  }
</style>
