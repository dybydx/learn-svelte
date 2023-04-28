<script lang="ts">
  import type ToDo from "../../../types/ToDo";
  import { v4 as uuid4 } from "uuid";

  export let todos: ToDo[] = [];

  let todoText = "";

  function addTodo() {
    const input = document.querySelector("input");
    const newTodo: ToDo = {
      id: uuid4(),
      title: todoText,
      completed: false,
    };
    todos = [...todos, newTodo];
    todoText = "";
  }
</script>

<ul>
  <form on:submit|preventDefault={addTodo}>
    <input bind:value={todoText} type="text" placeholder="Add a new todo" />
    <button type="submit">Add</button>
  </form>
  {#each todos as { id, title, completed }, index (id)}
    <li class:line-through={completed}>{index + 1} - {title}</li>
  {/each}
</ul>
