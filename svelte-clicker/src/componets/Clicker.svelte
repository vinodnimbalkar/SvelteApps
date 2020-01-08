<script>
  let count = 0;

  const incrementCount = () => {
    count += 1;
  };

  const decrementCount = () => {
    count -= 1;
  };

  const resetCount = () => {
    count = 0;
  };
</script>

<style>
  .clicker {
    height: 300px;
    width: 300px;
    margin: 0 auto;
    overflow: hidden;
  }

  .clicker-display {
    height: 200px;
  }

  .clicker-button-panel {
    height: 100px;
  }
</style>

<div class="container">
  <div class="clicker border border-secondary rounded">
    <div
      class="clicker-display d-flex align-items-center bg-light text-secondary">
      <div class="mx-auto display-1">{count}</div>
    </div>
    <div class="clicker-button-panel d-flex flex-row">
      <button class="btn btn-success w-100" on:click={incrementCount}>
        <i class="fas fa-plus fa-2x" />
      </button>
      <button class="btn btn-warning w-100" on:click={resetCount}>
        <i class="fa fa-sync-alt fa-2x" />
      </button>
      <button class="btn btn-danger w-100" on:click={decrementCount}>
        <i class="fas fa-minus fa-2x" />
      </button>
    </div>
  </div>
</div>
