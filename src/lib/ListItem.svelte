<script>
  export let item
  export let deleteItem
</script>

<div>
  <div class="itemContainer">
        <p class="item">{item}</p><span class="delete" on:click={deleteItem(item)}>X</span>
  </div>
</div>

<style>
  .itemContainer{
    display: flex;
    align-items: center;
    justify-content: center;
    margin: 0;
    font-size: 24px;
  }
  .delete{
    color: #f44336;
    opacity: 0.5;
    margin-left: 4px;
  }
  .delete:hover{
    opacity: 1;
    cursor: pointer;
  }
</style>