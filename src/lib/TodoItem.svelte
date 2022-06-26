<script lang="ts">
    import Icon from './Icon.svelte';

    import { todoList } from '../store';
    import type { Task } from '../types/interfaces';

    export let task: Task;
    export let completed: boolean;
    export let index: number;

    function complete(index: number): void {
        $todoList[index].completed = !$todoList[index].completed;
    }

    function remove(index: number): void {
        $todoList.splice(index, 1);
        $todoList = $todoList;
    }
</script>

<div class="todo" class:completed>
    <span class="todo__text">{task}</span>

    <div class="todo__buttons">
        <button class="complete" on:click={() => complete(index)}>
            <Icon name="check-mark" />
        </button>
        <button class="delete" on:click={() => remove(index)}>
            <Icon name="delete" />
        </button>
    </div>
</div>

<style>
    button.delete,
    button.delete:hover {
        color: brown;
        transition: color 100ms ease-out;
    }
    button.complete,
    button.complete:hover {
        color: cadetblue;
        transition: color 100ms ease-out;
    }

    .todo {
        display: flex;
        padding: 20px;
        border-radius: 20px;
        box-shadow: 0 0 15px rgb(0 0 0 / 20%);
        background-color: hsla(0, 0%, 100%, 0.2);
        margin-top: 1rem;
        font-size: 1.2rem;
        justify-content: space-between;
        align-items: center;
    }

    .todo__buttons {
        display: flex;
        align-items: center;
        margin-left: 1rem;
    }

    .todo button {
        width: 32px;
        height: 32px;
        padding: 4px;
        margin: 0;
        flex-shrink: 0;
    }
    .todo.completed {
        color: slategray;
    }
    .todo.completed .todo__text {
        text-decoration: line-through;
    }
    .todo.completed button {
        color: silver;
    }
</style>
