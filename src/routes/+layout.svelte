<script lang="ts">
    import { page } from '$app/stores';
</script>

<nav>
    <ul>
        <li aria-current={$page.url.pathname === '/' ? 'page' : undefined}>
            <a href="/">MON POKEDEX</a>
            <a href="/detail">MON POKEMON</a>
        </li>
    </ul>
</nav>

<main>
    <slot />
</main>

<style>

main {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-content: center;
    align-items: center;
    gap: 10px;
    font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
}

nav {
    font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
}

nav > ul {
    margin: 0px;
    padding: 20px 20px;
    border: 1px solid #333;
    border-radius: 50px;
    width: 350px;
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: center;
}

nav > ul > li {
    list-style-type: none;
}

nav > ul > li > a {
    margin: 0px 10px;
    text-decoration: none;
    font-weight: 800;
    color: black;
}

nav > ul > li > a:hover {
    color: whitesmoke;
}
</style>