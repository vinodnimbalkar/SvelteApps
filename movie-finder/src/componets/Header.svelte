<script>
  export let text;
</script>

<style>
  .App-header {
    background-color: #282c34;
    height: 70px;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    font-size: calc(10px + 2vmin);
    color: white;
    padding: 20px;
    cursor: pointer;
  }
  .App-header h2 {
    margin: 0;
  }
</style>

<header class="App-header">
  <h2>{text}</h2>
</header>
