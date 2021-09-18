<script>
  import { itemArray, emotionArray } from "../stores";
  let disabledStatus = true;
  let finalArr = [];

  function combineArr() {
    finalArr = $emotionArray.map((e, i) => e + ' ' + $itemArray[i])
  }

  $: {
    if ($emotionArray.length === 10 && $itemArray.length === 10) {
      disabledStatus = false;
    }
  }
</script>

<div class="container">
  <h3>Final List</h3>
  <button on:click={combineArr} disabled={disabledStatus}>Combine Thy Words</button>
  {#each finalArr as f}
  <p>{f}</p>
  {/each}
</div>

<style>
  .container {
    border: 1px solid black;
    height: 100%;
  }
  h3 {
    text-transform: uppercase;
    letter-spacing: 8px;
  }
</style>
