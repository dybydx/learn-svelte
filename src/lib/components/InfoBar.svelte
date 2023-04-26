<script lang="ts">
  export let message: string;
  export let type: string = "info";
  export let shadow: boolean = false;
</script>

<div
  class:error={type === "error"}
  class:success={type === "success"}
  class:info={type === "info" || !type}
  class:shadow
  class={`flex items-center justify-between border rounded gap-20 p-4 my-4 h-16`}
>
  <p>{message}</p>
</div>

<style lang="scss">
  .info {
    @apply bg-blue-100 text-blue-700 border-blue-700;
  }

  .success {
    @apply bg-green-100 text-green-700 border-green-700;
  }

  .error {
    @apply bg-red-100 text-red-700 border-red-700;
  }

  .shadow {
    @apply shadow-xl;
  }
</style>
