<script lang="ts">
    import Form from './lib/Form.svelte';
    import TodoList from './lib/TodoList.svelte';
</script>

<main>
    <h1>My to-do list</h1>
    <Form />
    <TodoList />
</main>

<style>
    :global(body) {
        margin: 0;
    }

    :global(input, button, select, textarea) {
        font-family: inherit;
        font-size: inherit;
        -webkit-padding: 0.4em 0;
        padding: 0.4em;
        margin: 0 0 0.5em 0;
        box-sizing: border-box;
        border: 1px solid #ccc;
        border-radius: 2px;
    }

    :global(button) {
        background-color: transparent;
        outline: none;
        border: none;
        cursor: pointer;
    }

    :root {
        font-family: 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans',
            'Helvetica Neue', sans-serif;
        -webkit-font-smoothing: antialiased;
        -moz-osx-font-smoothing: grayscale;
    }

    main {
        display: flex;
        flex-direction: column;
        align-items: center;
        min-height: 100vh;
        padding: 5vmin;
        box-sizing: border-box;
        background: antiquewhite;
    }

    h1 {
        text-align: center;
        font-size: 1.5rem;
        margin: 2em 0;
    }
</style>
