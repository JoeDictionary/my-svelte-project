<script>
  import TodoItem from "./TodoItem.svelte";

  let newTodoItem = "";
  let currentFilter = "all";
  let nextId = 4;

  let todos = [
    {
      id: 1,
      title: "My first todo",
      completed: false
    },
    {
      id: 2,
      title: "My second todo",
      completed: false
    },
    {
      id: 3,
      title: "My third todo",
      completed: false
    }
  ];
</script>


<div class="container">
  <!-- <img src={""} alt=""> -->
  <h2> Svelte Todo App </h2>
  <input type="text" class="todo-input" placeholder="Insert todo item ..." bond:value={newTodoItem} on:keydown={addTodo}>

  {#each filteredTodos as todo}
    <div class="todo-item">
      <TodoItem {...todo} on :delete>

      </TodoItem>
    </div>
  {/each}
</div>
