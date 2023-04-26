<script lang="ts">
  import { v4 as uuidv4 } from "uuid";
  import ToDoList from "./lib/components/todos/ToDoList.svelte";
  const todos = [
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
</script>

<div class="container w-5/6 mx-auto">
  <ToDoList {todos} />
</div>

<style lang="scss">
</style>
