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

  function handleAddToDo(event) {
    event.preventDefault();
    todos = [
      ...todos,
      { id: uuidv4(), title: event.detail.title, completed: false },
    ];
  }
</script>

<div class="container w-5/6 mx-auto my-6">
  <ToDoList {todos} on:addTodo={handleAddToDo} />
</div>

<style lang="scss">
</style>
