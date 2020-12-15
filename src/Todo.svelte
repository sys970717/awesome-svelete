<script>
    export let todo;
    export let todos;

    let isEdit = false;
    let title = '';

    function onEdit() {
        isEdit = true;
        title = todo.title;
    }
    function offEdit() {
        isEdit = false;
    }

    function updateTodo() {
        todo.title = title;
        offEdit();
    }

    function onDelete() {
        $todos = $todos.filter(t => t.id !== todo.id);
    }
</script>

<div>
    {#if isEdit}
        <div>
            <input bind:value={title}
                on:keydown={(e) => {e.key === 'Enter' && updateTodo()}} type="text" />
            <button on:click={updateTodo}> OK </button>
            <button on:click={offEdit}> Cancel </button>
        </div>
    {:else}
    {todo.title}
    <button on:click={onEdit}> Edit </button>
    <button on:click={onDelete}> Delete </button>
    {/if}
</div>
