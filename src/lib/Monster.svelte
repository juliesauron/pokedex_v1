<script lang="ts">
    import type { IndexMonster } from "../routes/+page";

    export let monster: IndexMonster;

</script>

<!-- svelte-ignore a11y-click-events-have-key-events -->
<!-- svelte-ignore a11y-no-static-element-interactions -->
<div class="monster" > <!--on:click={() => monsterClick(monster)} -->
    <div class="monster-content">
        <img src="{monster.image}" alt="{monster.name}">
        {monster.name}
    </div>
    <div class="monster-id">
        {monster.id}
    </div>
</div>

<style>
    .monster {
    width: 100px;
    border: 1px solid rgba(0, 0, 0, 0.1);
    border-radius: 10px;
    padding: 10px;
    
    position: relative;
}

.monster:hover {
    background-color: rgba(0, 0, 0, 0.1);
}

.monster-id {
    position: absolute;
    top: 8px;
    left: 8px;
    color: black;
    font-size: 0.6em;
}

.monster-content {
    display: flex;
    flex-direction: column;
    align-items: center;
}
</style>
