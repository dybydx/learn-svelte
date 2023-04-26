<script lang="ts">
  import MdInfoOutline from "svelte-icons/md/MdInfoOutline.svelte";
  import MdAddCircleOutline from "svelte-icons/md/MdAddCircleOutline.svelte";
  import MdCheck from "svelte-icons/md/MdCheck.svelte";

  export let type: string = "info";
  export let shadow: boolean = false;
  console.log($$slots);
</script>

<div
  class:error={type === "error"}
  class:success={type === "success"}
  class:info={type === "info" || !type}
  class:shadow
  class={`flex items-center justify-start border rounded gap-4 p-4 my-4 h-16`}
>
  <div class="icon">
    {#if type === "error"}
      <div style="transform: rotate(45deg)"><MdAddCircleOutline /></div>
    {:else if type === "success"}
      <MdCheck />
    {:else}
      <MdInfoOutline />
    {/if}
  </div>

  <p><slot>No message defined</slot></p>
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

  .icon {
    width: 30px;
  }
</style>
