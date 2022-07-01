<script>
    export let list;
</script>

<ul>
    {#each list as listItem }
        <li class:bought={listItem.bought}>
        <input type=checkbox bind:checked={listItem.bought}>
        <span>{listItem.item}</span>
        <span>{listItem.quantity}</span>
        </li>
    {/each}
</ul>

<style>
    .bought {
        text-decoration: line-through;
    }
</style>