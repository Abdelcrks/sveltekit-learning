<h1>Welcome to SvelteKit</h1>
<p>Visit <a href="https://svelte.dev/docs/kit">svelte.dev/docs/kit</a> to read the documentation</p>


<script>
    let count = 0

    const click = () => {
        count += 1
    }
    
    let name = ""

    let show = true

    const showClick = ( ) => {
        if(show === true){
            show = false
        }
        else{
            show = true
        }

    }


    let showV2 = true

    const showClickV2 = () => {
        showV2 = !showV2
    }

    let todos = []
    let newTodo = ""

    const addTodo = () => {
        const value = newTodo
        todos = [...todos, value]
        newTodo = ""
    }

</script>

<button on:click={click}>clique</button>
<p>compteur : {count}</p>

<input bind:value={name}/>
<p>Salut {name}</p>

<button on:click={showClick}>{show}</button>

<button on:click={showClickV2}>{showV2}</button>


<p>todo :</p>

<form on:submit|preventDefault={addTodo}>
<input bind:value={newTodo}/>
<button>Ajouter à la todo</button>
</form>


{#each todos as item}
<li>Tâche :{item}</li>
{/each}