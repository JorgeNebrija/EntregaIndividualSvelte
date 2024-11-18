<script>
    let search = "";
    const items = ['Manzana', 'Banana', 'Pera', 'Naranja'];
    
    function filterItems(){
        return items.filter(item=>
            item.toLowerCase().includes(search.toLowerCase())
        );
    }
</script>

<div class="container">
    <h1>Buscador</h1>
    <input type= "text" bind:value={search} placeholder="Buscar..."/>
    
    <ul>
        {#each filterItems() as item}
            <li>{item}</li>
        {/each}
    </ul>
</div>