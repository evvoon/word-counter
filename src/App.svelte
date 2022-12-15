<script>
  import { onMount } from "svelte";

  let textInput = null;
  let wordCount = 0;

  onMount(() => {
    textInput = document.querySelector(".text-input");

    textInput.addEventListener("input", () => {
      const splitted = textInput.value.trim().split(/[\s-]/);
      wordCount = splitted.length;
    });
  });
</script>

<h1>WORD COUNTER</h1>

<div>{wordCount}</div>

<textarea class="text-input" cols="30" rows="10" placeholder="Start typing" />

<style>
  textarea {
    font-size: 32px;
    font-family: "Jetbrains Mono";
    background-color: rgb(33 33 53);
    color: rgb(27 179 184);

    padding: 20px; /* space on the inside */
    margin: 1rem; /* space on the outside */

    width: 1100px;
    height: 500px;

    border: none;
    overflow: auto;
    outline: none;

    -webkit-box-shadow: none;
    -moz-box-shadow: none;
    box-shadow: none;

    /* border: 1px 10; */
    /* border-radius: 4px; */
  }

  div {
    font-family: monospace;
    font-size: 40px;
    color: rgb(191 60 136);
  }
</style>
