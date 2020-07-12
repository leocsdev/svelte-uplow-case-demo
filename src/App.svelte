<script>
  let headTitle = 'Svelte Uppercase/Lowercase Demo';
  let text = '';

  function handleText(event) {
    const textTyped = event.target.value;
    text = textTyped;
  }

  function handleLowerCase() {
    const lowerText = text.toLowerCase();
    text = lowerText;
  }

  function handleUpperCase() {
    const upperText = text.toUpperCase();
    text = upperText;
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
    placeholder="Type here..." />

  <!-- Output Text -->
  <textarea
    name="text-output"
    cols="30"
    rows="10"
    value={text}
    disabled
    placeholder="Output goes here" />

  <br />

  <!-- Buttons -->
  <button on:click={handleLowerCase}>Lower Case</button>
  <button on:click={handleUpperCase}>Upper Case</button>

</main>

<style>
  main {
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
</style>
