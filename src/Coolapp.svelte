<script>
    let coolNote = '';
    let coolList = '';
//MAKING AN ARRAY
    function addCoolList() {
        if (!coolNote) return;
        coolList = [...coolList, {
            text: coolNote,
            status: false
    }];
    coolNote = '';
}
//REMOVING ITEMS IN THE ARRAY
    function removeFromList(index) {
        coolList.splice(index, 1);
        coolList = coolList;
    }
</script>

<p>Type and hit ENTER to add it to the list!</p>
<form on:submit|preventDefault={addCoolList}>
    <input bind:value={coolNote}>
</form>

<ol class="list">
    {#each coolList as item, index}
    <li>
    <input bind:checked={item.status} class="checkbox" type="checkbox">    
    <span class:checked={item.status}> {item.text}</span>
    <button class="button" on:click={() => removeFromList(index)}>X</button>
    </li>
    {/each}
</ol>

<style>
    .list {
        list-style: none;
    }
   .button {
       border-radius: 50%;
       background-color: lightcoral;
   }
</style>