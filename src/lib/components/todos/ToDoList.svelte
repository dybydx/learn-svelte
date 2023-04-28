<svelte:options immutable={true} />

<script lang="ts">
  import type ToDo from "../../../types/ToDo";
  import { createEventDispatcher } from "svelte";

  export let todos: ToDo[] = [];
  let todoText = "";

  const dispatch = createEventDispatcher();

  function addTodo() {
    dispatch(
      "addTodo",
      {
        title: todoText,
      },
      { cancelable: true }
    );
    todoText = "";
  }
</script>

<form on:submit|preventDefault={addTodo}>
  <input bind:value={todoText} type="text" placeholder="Add a new todo" />
  <button type="submit">Add</button>
</form>
<ul>
  {#each todos as { id, title, completed }, index (id)}
    <li class:line-through={completed}>{index + 1} - {title}</li>
  {/each}
</ul>
