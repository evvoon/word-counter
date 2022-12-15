<script>
  import { wordsCount } from "words-count";

  let inputValue = "";
  $: wordCount = wordsCount(inputValue);

  function resize(e) {
    console.log(e);
    e.target.style.height = "";
    e.target.style.height = Math.max(e.target.scrollHeight, 600) + "px";
  }
</script>

<h1>word counter</h1>
<div>{wordCount}</div>

<textarea
  on:input={resize}
  cols="30"
  rows="10"
  placeholder="Start typing"
  bind:value={inputValue}
/>

<style>
  textarea {
    font-size: 32px;
    font-family: "Jetbrains Mono";
    background-color: rgb(33 33 53);
    color: rgb(27 179 184);

    padding: 20px; /* space on the inside */
    margin: 1rem; /* space on the outside */

    width: 95vw;
    height: 500px;

    border: none;
    overflow: auto;
    outline: none;

    -webkit-box-shadow: none;
    -moz-box-shadow: none;
    box-shadow: none;
  }

  div {
    font-size: 2rem;
    color: rgb(191 60 136);
    position: fixed;
    bottom: 50px;
    right: 50px;
  }
</style>
