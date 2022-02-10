<header>
    <a href="/">Home</a>
    <h1>Blog</h1>
</header>

<style lang="scss">
    :global(body), * {
        padding: 0;
        margin: 0;
    }

    header {
        display: flex;
        flex-direction: row;
        width: 100%;
        height: 3rem;
        background: #222;
        color: #eee;
        align-items: center;

        h1 {
            margin: auto;
        }

        a {
            position: absolute;
            text-decoration: none;
            font-weight: bold;
            font-size: large;
            color: #ddd;
            padding: 15px;
            transition: 0.2s;

            &:hover {
                color: #fff;
            }
        }
    }
</style>