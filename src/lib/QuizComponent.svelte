<script>
  export let goToSlide;
  export let updateChoice;

  let questions = [
    {
      text: "How would you describe the type of music you listen to?",
      options: [
        { text: "Upbeat and energetic", result: "Hip Hop" },
        { text: "Slow and smooth", result: "English Waltz" },
        { text: "A mix of the two", result: "Salsa" }
      ],
      selected: null
    },
    {
      text: "Do you prefer more intricate or freeform movements?",
      options: [
        { text: "Freeform", result: "Hip Hop" },
        { text: "Intricate", result: "English Waltz" },
        { text: "A little bit of both", result: "Salsa" }
      ],
      selected: null
    },
    {
      text: "Are you a fast learner?",
      options: [
        { text: "Yes", result: "Salsa" },
        { text: "No", result: "English Waltz" },
        { text: "Somewhat", result: "Hip Hop" }
      ],
      selected: null
    }
  ];

  let currentQuestionIndex = 0;
  let submitted = false;
  let result = "";

  function nextQuestion() {
    if (currentQuestionIndex < questions.length - 1) {
      currentQuestionIndex++;
    } else {
      submitQuiz();
    }
  }

  function submitQuiz() {
    submitted = true;

    // Count occurrences of each result type
    let counts = { "Hip Hop": 0, "English Waltz": 0, "Salsa": 0 };

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
  <h2>Which dance style suits you?</h2>

  {#if !submitted}
    <div class="question">
      <h3>{questions[currentQuestionIndex].text}</h3>
      {#each questions[currentQuestionIndex].options as option}
        <label class="radio-label">
          <input
            type="radio"
            bind:group={questions[currentQuestionIndex].selected}
            value={option}
            on:change={nextQuestion}
          />
          <span class="custom-radio"></span>
          {option.text}
        </label>
      {/each}
    </div>
  {/if}

  {#if submitted}
    <div class="results">
      <h2>Your Result: {result}</h2>
    </div>
  {/if}
</main>

<style>
  @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@400;700&display=swap');

  main {
    color: white;
    padding: 20px;
    border-radius: 10px;
  }

  h2 {
    font-family: 'Poppins', sans-serif;
    font-size: 2rem;
    margin-bottom: 20px;
  }

  .question {
    margin-bottom: 30px;
  }

  .question label {
    display: flex;
    align-items: center;
    margin-top: 10px;
    font-size: 1.2rem;
    cursor: pointer;
  }

  .radio-label {
    position: relative;
    padding-left: 35px;
  }

  .radio-label input {
    position: absolute;
    opacity: 0;
    cursor: pointer;
  }

  .custom-radio {
    position: absolute;
    top: 0;
    left: 0;
    height: 20px;
    width: 20px;
    background-color: white;
    border-radius: 50%;
    border: 2px solid #FE2C55;
    transition: background-color 0.3s ease, transform 0.3s ease;
  }

  .radio-label input:checked ~ .custom-radio {
    background-color: #FE2C55;
    transform: scale(1.2);
  }

  .radio-label input:checked ~ .custom-radio::after {
    content: '';
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    width: 10px;
    height: 10px;
    background-color: white;
    border-radius: 50%;
  }

  .results {
    margin-top: 20px;
    font-family: 'Poppins', sans-serif;
    font-size: 1.5rem;
  }
</style>
