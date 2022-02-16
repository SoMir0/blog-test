<script lang="ts">
    import Header from "./Header.svelte";
    import supabase from '$lib/db'
    async function getData() {
        const { data, error } = await supabase
            .from('Posts')
            .select()
        if (error) throw new Error(error.message)
        console.log(data);
        
        return data
    }
</script>

<main>
    <Header />
    {#await getData()}
        <p>Fetching data...</p>
        {:then data}
            {#each data as post}
                <article>
                    <h2>{post.title}</h2>
                    <hr>
                    <p>{post.desc}</p>
                </article>
            {/each}
        {:catch error}
            <p>Something went wrong while fetching the data:</p>
            <pre>{error}</pre>
    {/await}
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