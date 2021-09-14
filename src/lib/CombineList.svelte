<script>
  import {itemArray, emotionArray} from '../stores'
  let disabledStatus = true;

  $: {
    if($emotionArray.length === 10 && $itemArray.length === 10){
      disabledStatus = false
      console.log('test', $emotionArray, $itemArray)
    }
  }
</script>

<div class="container">
  <h3>Final List</h3>
  <button disabled={disabledStatus}>Combine Thy Words</button>
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