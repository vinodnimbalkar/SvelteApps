<script>
  export let search;
  $: searchValue = "";

  const handleSearchInputChanges = e => {
    searchValue = e.target.value;
  };

  const resetInputField = () => {
    searchValue = "";
  };

  const callSearchFunction = e => {
    e.preventDefault();
    search(searchValue);
    resetInputField();
  };
</script>

<style>
  .search {
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    justify-content: center;
    margin-top: 10px;
  }

  input[type="submit"] {
    padding: 5px;
    background-color: transparent;
    color: black;
    border: 1px solid black;
    width: 80px;
    margin-left: 5px;
    cursor: pointer;
  }

  input[type="submit"]:hover {
    background-color: #282c34;
    color: antiquewhite;
  }

  .search > input[type="text"] {
    width: 40%;
    min-width: 170px;
  }
</style>

<form class="search">
  <input type="text" bind:value={searchValue} on:change={handleSearchInputChanges} />
  <input type="submit" value="SEARCH" on:click={callSearchFunction} />
</form>
