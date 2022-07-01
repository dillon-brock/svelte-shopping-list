<script>
    export let adding;
</script>

{#if !adding}
    <button on:click>Add New List</button>
  {:else}
    <form on:submit>
      <label>
        Give Your New List A Name:
        <input name="name">
      </label>
      <button>Add List</button>
    </form>
{/if}