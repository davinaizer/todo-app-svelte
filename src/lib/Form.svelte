<script lang="ts">
    import type { Task } from 'src/types/interfaces';

    import { todoList } from '../store';

    let newItem = '';

    function addTask(): void {
        if (newItem !== '') {
            const newTask: Task = {
                task: newItem,
                completed: false
            };

            newItem = '';
            $todoList = [...$todoList, newTask];
        }
    }
</script>

<form on:submit|preventDefault={addTask}>
    <input bind:value={newItem} placeholder="Enter to-do" />

    <button class="add-todo" on:click={addTask}><span>+</span></button>
</form>

<style>
    form {
        width: 100%;
        max-width: 500px;
        display: flex;
        align-items: center;
        margin-bottom: 1rem;
    }

    input {
        flex-grow: 1;
        width: 0;
        border: none;
        border-bottom: 1px solid black;
        background: transparent;
        box-shadow: none;
        font-size: 1.2rem;
        margin: 0;
        outline: none;
    }

    .add-todo {
        width: 2rem;
        height: 2rem;
        margin: 0;
        background: transparent;
        border: 1px solid black;
        border-radius: 100%;
        flex-shrink: 0;
        margin-left: 1rem;
    }

    .add-todo span {
        display: flex;
        align-items: center;
        justify-content: center;
        line-height: 0;
    }
</style>
