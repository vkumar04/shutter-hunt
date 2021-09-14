<script>
  import {emotionArray} from '../stores'
  import ListItem from './ListItem.svelte'
  let emotion = '';

  function handleClick() {
    $emotionArray = [...$emotionArray, emotion]
    emotion = ''
  }

  function deleteEmotion(i) {
    const filteredEmotion = $emotionArray.filter((index) => index !== i)
    $emotionArray = filteredEmotion
  }
</script>

<div class="container">
  <h3>Emotion List</h3>
  <input bind:value={emotion} placeholder="enter a emotion" />
  <button disabled={emotion === '' && $emotionArray.length <= 10} on:click={handleClick}>Submit</button>
 <div>
   {#each $emotionArray as emo, i}
    <ListItem item={emo} deleteItem={deleteEmotion} />
   {/each}
 </div>
</div>

<style>
  .container{
    border: 1px solid black;
    height: 100%;
  }
  h3{
    text-transform: uppercase;
    letter-spacing: 8px;
  }
</style>