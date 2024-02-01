<script lang="ts">

import type { PageData } from "./$types";
import Monster from "../lib/Monster.svelte";


export let data: PageData;

let searchString = ''
$: selectedMonsters = data.monsters.filter((monster) => {
    return monster.name.toLocaleLowerCase().includes(searchString.toLocaleLowerCase())
})

</script>

<div>
    <input class="search-field" type="text" bind:value={searchString} placeholder="Rechercher un pokemon" />
</div>


<div class="monsters">
    {#each selectedMonsters as monster (monster.id)}
    <a href="/detail/{monster.id}">
        <Monster monster={monster} />
    </a>
    {/each}
</div>

<style>

.monsters {
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    justify-content: center;
    gap: 10px;
    width: 60%;
    min-width: 400px;
}

.monsters > a {
    text-decoration: none;
    cursor: pointer;
    color: black;
}

.search-field {
    padding: 10px 20px;
    border: 1px solid #333;
    border-radius: 20px;
    width: 350px;
    background-color: rgba(0, 0, 0, 0);
    color: black;
}

.search-field::placeholder{
    color: black;
}
</style>