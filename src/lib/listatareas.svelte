<script>
    let task = '';
    let priority = 'media';  // Por defecto, prioridad media
    let tasks = [];

    function addTaskPush(){
        console.log(tasks.push({ text: task, priority }))
        //tasks=tasks.push({text:task,priority})
    }
    // Función para agregar una nueva tarea
    function addTask() {       
            tasks = [
                ...tasks,
                { text: task, priority }
            ];
            task = '';
            priority = 'media';  // Reiniciar el campo de prioridad       
        sortTasks();
    }

    // Función para ordenar las tareas por prioridad
    function sortTasks() {
        tasks.sort((a, b) => {
            const priorityOrder = { alta: 1, media: 2, baja: 3 };
            return priorityOrder[a.priority] - priorityOrder[b.priority];
        });
    }

    // Función para eliminar una tarea
    function deleteTask(index) {
        tasks = tasks.filter((_, i) => i !== index);
    }
</script>

<style>
    .alta { color: red; }
    .media { color: orange; }
    .baja { color: green; }
</style>
<div class="container">
<h1>Lista de tareas con prioridad</h1>

<div>
    <input type="text" bind:value={task} placeholder="Nueva tarea" />
    
    <select bind:value={priority}>
        <option value="alta">Alta</option>
        <option value="media">Media</option>
        <option value="baja">Baja</option>
    </select>

    <button on:click={addTaskPush}>Agregar tarea con Push</button>
    <button on:click={addTask}>Agregar tarea con Spread Operator</button>
</div>

<ul>
    {#each tasks as { text, priority }, index}
        <li class={priority}>
            {text} - {priority} 
            <button on:click={() => deleteTask(index)}>Eliminar</button>
        </li>
    {/each}
</ul>
</div>