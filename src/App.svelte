<script lang="ts">
  import InfoBar from "./lib/components/InfoBar.svelte";

  let name = "Prathamesh";
</script>

<div class="container w-5/6 mx-auto">
  <h1>Hello, {name}</h1>
  <InfoBar message="Hello, World!" shadow />
  <InfoBar message="Hello, World!" type="success" />
  <InfoBar message="Hello, World!" type="error" shadow />
</div>

<style lang="scss">
  h1 {
    @apply text-purple-700;
  }
</style>
