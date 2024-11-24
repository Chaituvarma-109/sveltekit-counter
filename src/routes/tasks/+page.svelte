<script>
    let inp_task = $state('');
    let tasks = $state([
        {'done': false, 'todo': 'task1'},
        {'done': false, 'todo': 'task2'},
    ]);

    function add() {
        tasks.unshift({'done': false, 'todo': inp_task});
    }

    function remove() {
        tasks.filter(task => !task.done)
    }
</script>
<br>
<input type="text" placeholder="Enter task name" bind:value={inp_task}/>
<button type="submit" onclick={add}>Create</button>
<button type="submit" onclick={remove}>Clear</button>
<hr>
<h3>Total tasks {tasks.length}</h3>
<ul>
    {#each tasks as task}
        <li>
            <input type="checkbox" bind:checked={task.done}/>
            {task.todo}
        </li>
        <br>
    {/each}
</ul>
