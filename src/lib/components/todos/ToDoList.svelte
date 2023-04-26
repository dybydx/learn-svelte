<script lang="ts">
  import type ToDo from "../../../types/ToDo";

  export let todos: ToDo[] = [];
</script>

<ul>
  {#each todos as { id, title, completed }, index (id)}
    <li class:line-through={completed}>{index + 1} - {title}</li>
  {/each}
</ul>
