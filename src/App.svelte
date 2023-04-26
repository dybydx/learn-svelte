<script lang="ts">
  import InfoBar from "./lib/components/InfoBar.svelte";

  let name = "Prathamesh";
</script>

<div class="container w-5/6 mx-auto">
  <h1>Hello, {name}</h1>
  <InfoBar shadow>Hello, {name}</InfoBar>
  <InfoBar type="success">What's up</InfoBar>
  <InfoBar type="error" shadow />
</div>

<style lang="scss">
  h1 {
    @apply text-purple-700;
  }
</style>
