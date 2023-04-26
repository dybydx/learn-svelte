<script lang="ts">
  let count = 0;
  function increment() {
    count += 1;
  }

  function decrement() {
    count -= 1;
  }
</script>

<div class="flex items-center-justify-center">
  <h2 class="text-4xl">{count}</h2>
</div>
<div class="flex items-center-justify-center gap-4">
  <button on:click={increment}>Increment</button>
  <button on:click={decrement}>Decrement</button>
</div>
