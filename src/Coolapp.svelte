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

    p{ 
        color: #f08080;
    }
    .list {
        color: #f08080;
        list-style: none;
        font-size: 2em;
        
    }
    .checkbox {
        margin-right: 2vw;
    }
   .button {
       font-size: 0.4em;
       border-radius: 50%;
       margin-left: 1em;
       padding-left: 0.5em;
       padding-right: 0.5em;
       background-color: #f08080;
   }
</style>
