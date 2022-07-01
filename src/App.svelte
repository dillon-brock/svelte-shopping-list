<script>
  import ShoppingList from "./lib/ShoppingList.svelte";
  import AddList from './lib/AddList.svelte';

  let numOfLists = 2;
  let listNames = ['Sunday List', 'Monday List'];
  let adding = false;

  let newName;

  function toggleAdding() {
    adding = !adding;
  }

  function addList(e) {
    e.preventDefault();
    const formData = new FormData(e.target);
    let name = (formData.get('name')).toString();
    listNames = [...listNames, name];
    toggleAdding();
  }

</script>

<main>
  {#each listNames as name}
  <ShoppingList name={name}/>
  {/each}
  <AddList adding={adding} on:click={toggleAdding} on:submit={addList}/>

</main>

<style>
  
</style>
