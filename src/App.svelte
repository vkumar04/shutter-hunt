<script>
  import Header from "./lib/Header.svelte";
  import EmotionList from "./lib/EmotionList.svelte";
  import ItemList from "./lib/ItemList.svelte";
  import CombineList from "./lib/CombineList.svelte";
</script>

<main>
  <Header />
  <div class="container">
    <EmotionList />
    <CombineList  />
    <ItemList />
  </div>
</main>

<style>
  :root {
    font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen,
      Ubuntu, Cantarell, "Open Sans", "Helvetica Neue", sans-serif;
  }
  main {
    text-align: center;
    padding: 1em;
    margin: 0 auto;
  }
  .container {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    grid-template-rows: 1fr;
    grid-column-gap: 12px;
    grid-row-gap: 0px;
    text-align: center;
    height: 75vh;
  }
</style>
