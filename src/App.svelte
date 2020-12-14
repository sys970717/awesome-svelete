<script>
	import Todo from './Todo.svelte';

    let title = "";
	let todos = [];
	let id = 0;
	
	function createTodo() {
		console.log(title);
		todos.push({
			id,
			title,
		});
		todos = todos;
		title = '';
		id += 1;
	};
</script>

<input type="text" 
	   bind:value={title}
	   on:keydown={(e) => { e.key === 'Enter' && {createTodo()}} } />
<button on:click={createTodo}> Cretae Todo </button>

{#each todos as todo}
	<Todo todo />
{/each}
