<script>
  import {itemArray} from '../stores'
  import ListItem from './ListItem.svelte'
  let item = '';
  function handleClick() {
    $itemArray = [...$itemArray, item]
    item = ''
  }

  function deleteItem(i) {
    const filteredItems = $itemArray.filter((index) => index !== i)
    $itemArray = filteredItems
  }
</script>

<div class="container">
  <h3>Item List</h3>
  <input bind:value={item} placeholder="enter a item" />
  <button disabled={item === '' || $itemArray.length === 10} on:click={handleClick}>Submit</button>
 <div>
   {#each $itemArray as itm, i}
    <ListItem item={itm} deleteItem={deleteItem} />
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