<script>
    import {goto} from "$app/navigation";

    let inputValue = '';
    let active = false;

    function cancelInactive() {
        active = !!inputValue;
    }

    function submitSearch() {
        goto('/search/'+inputValue)
    }

</script>

<form class="search" on:submit|preventDefault={submitSearch}>

    {#if !active}
        <label>Search Movies</label>
    {/if}

    <input
            bind:value = {inputValue}
            on:blur = {cancelInactive}
            on:focus={() => active = true}
            placeholder="search"
            type="text" >
    {#if inputValue}
        <button >Search</button>
    {/if}
</form>

<style>

    form {
        width: 30%;
        margin: 1rem;
        align-self: center;
    }
    button {
        font-size: 1rem;
        margin-top: .5rem;
        padding: 0  1rem;
        background-color: rgb(96 , 120 , 201);
        color: white;
        border: none;
        cursor: pointer;
    }
    input {
        display: block;
        width: 100%;
    }
</style>

