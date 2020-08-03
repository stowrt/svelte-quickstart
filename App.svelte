<script>
  let todos = [];
  let todo = "";
  let addTodo = () => {
    console.log(todo);
    todos = [...todos, todo];
    console.log(todos);
  };
  let removeTodo = index => {
    todos = [...todos.slice(0, index), ...todos.slice(index + 1)];
  };
  let completeTodo = index => {
    console.log(todos[index]);
  };
</script>
<main>
<input bind:value={todo} type="text"/>
<button on:click={addTodo}>add</button>
<ul>
{#each todos as todo, index}
  <li on:click={()=>completeTodo(index)}>{todo}</li>
  <button on:click={()=>removeTodo(index)}>X</button>
{/each}
</ul>
</main>