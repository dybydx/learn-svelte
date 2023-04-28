<script lang="ts">
  import { v4 as uuidv4 } from "uuid";
  import ToDoList from "./lib/components/todos/ToDoList.svelte";
  let todos = [
    {
      id: uuidv4(),
      title: "Learn Svelte",
      completed: false,
    },
    {
      id: uuidv4(),
      title: "Learn TypeScript",
      completed: true,
    },
    {
      id: uuidv4(),
      title: "Learn Tailwind CSS",
      completed: false,
    },
  ];

  $: {
    console.log(todos);
  }
</script>

<div class="container w-5/6 mx-auto my-6">
  <h1>Total items in todo {todos.length}</h1>
  <ToDoList bind:todos />
</div>

<style lang="scss">
</style>
