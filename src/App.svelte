<script>
  let headTitle = 'Uppercase/Lowercase Conversion';
  let text = '';
  let textOutput = '';

  function handleText(event) {
    text = event.target.value;
  }

  function handleLowerCase() {
    const lowerText = text.toLowerCase();
    textOutput = lowerText;
  }

  function handleUpperCase() {
    const upperText = text.toUpperCase();
    textOutput = upperText;
  }

  function handleClear() {
    text = '';
    textOutput = '';
  }
</script>

<main>
  <h1>{headTitle}</h1>

  <!-- Input Text -->
  <textarea
    name="text-input"
    cols="30"
    rows="10"
    on:input={handleText}
    value={text}
    placeholder="Type here..." />

  <!-- Output Text -->
  <textarea
    name="text-output"
    cols="30"
    rows="10"
    value={textOutput}
    disabled
    placeholder="Output goes here" />

  <br />

  <!-- Buttons -->
  <button on:click={handleLowerCase}>lowercase</button>
  <button on:click={handleUpperCase}>UPPERCASE</button>
  &nbsp; &nbsp;
  <button on:click={handleClear}>Clear</button>
</main>

<style>
  main {
    text-align: center;
    max-width: 1200px;
    margin: 0 auto;
  }

  h1 {
    color: purple;
    font-size: 2em;
    font-weight: 400;
  }

  textarea:disabled {
    background-color: white;
    color: black;
  }

  @media (max-width: 1200px) {
    main {
      margin: 0 5%;
    }
  }

  @media (max-width: 768px) {
    h1 {
      font-size: 1.5em;
      font-weight: 400;
    }
  }
</style>
