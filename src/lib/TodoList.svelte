<script lang="ts">
    import { todoList } from '../store';

    import TodoItem from './TodoItem.svelte';
</script>

<div class="todo-list">
    {#each $todoList as item, index}
        <TodoItem {...item} {index} />
    {/each}
</div>

<style>
    .todo-list {
        width: 100%;
        max-width: 500px;
    }
</style>
