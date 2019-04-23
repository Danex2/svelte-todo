<script>
	let todos = [];
	let todo = "";

	function addTodo() {
	  todos = [
	    ...todos,
	    {
	      id: Math.random(),
	      text: todo
	    }
	  ];
	  todo = "";
	}

	function clearTodos() {
	  todos = [];
	}
</script>

<style>
</style>

<h1>Todo app made with Svelte!</h1>
<form on:submit|preventDefault={addTodo}>
<input type="text" bind:value={todo} placeholder="Add todo!">
<button>Add</button>
</form>
<button on:click={clearTodos}>Clear</button>
<ul>
{#each todos as todo}
	<li>{todo.text}</li>
{/each}
</ul>
