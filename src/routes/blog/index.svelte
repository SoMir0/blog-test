<script lang="ts">
    import Header from "./Header.svelte";
</script>

<main>
    <Header />
    {#each [0, 1, 2, 3] as cat}
        <article>
            <h2>Title</h2>
            <hr>
            <p>Lorem ipsum, dolor sit amet consectetur adipisicing elit. Fugiat aspernatur eveniet aliquid rem ratione laboriosam quis, illum quaerat, repellendus aut quae ea, iste ad. Fuga commodi expedita eveniet eos molestias!</p>
        </article>
    {/each}
</main>

<style lang="scss">
    :global(body), main {
        background: #3d3f43;
        color: #eee;
    }

    article {
        display: inline-block;
        max-width: 60vw;
        padding: 1rem;
        margin: 1rem;
        margin-left: 5rem;
        border-radius: 25px;
        background: #2c2e32;
    }
</style>