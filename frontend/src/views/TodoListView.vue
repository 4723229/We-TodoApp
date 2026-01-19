<script setup lang="ts">
    import { useTodoStore } from '../stores/todoStore';
    const todoStore = useTodoStore();
</script>

<template>
    <section class="todo-app">
        <h2>Todos</h2>
        <ul>
            <li
                v-for="todo in todoStore.todos"
                :key="todo.id"
                style="display: flex; align-items: center; gap: 0.5rem; margin:0.25rem 0;"
            >
                <input type="checkbox" v-model="todo.completed" />
                <span :style="{ textDecoration: todo.completed ? 'line-through' : 'none' }">
                    <routerLink :to="{ name: 'TodoDetail', params: { id: todo.id } }">{{ todo.title }}</routerLink>
                </span>
                <button v-on:click="todoStore.deleteTodo(todo.id)">Remove</button>
            </li>
        </ul>
    </section>
<section>
    <AddTodo />
</section>
</template>