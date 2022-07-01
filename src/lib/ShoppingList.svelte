<script>
    import AddItemForm from "./AddItemForm.svelte";
    import ItemList from "./ItemList.svelte";

    export let name;

    let list = [];
    let inputValue;
    let quantValue;

    function handleAddItem(e) {
        e.preventDefault();
        const formData = new FormData(e.target);
        const data = {bought: false};
        for (let field of formData) {
            let [key, value] = field;
            data[key] = value;
        }
        data.quantity = Number(data.quantity);
        list = [...list, data];
        e.target.reset();

    }

    function handleClearList() {
    list = [];
    }

</script>


<h2>{name}</h2>
<AddItemForm on:submit={handleAddItem}/>
<ItemList list={list}/>
<button on:click={handleClearList}>Clear List</button>