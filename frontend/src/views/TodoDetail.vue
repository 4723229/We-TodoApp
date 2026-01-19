<script setup lang="ts">
    import { useTodoStore } from '../stores/todoStore';
    import { useRoute } from 'vue-router';
    const todoStore = useTodoStore();
    const route = useRoute();
    const todoId = Number(route.params.id);
</script>

<template>
    <section class="todo-detail">
        <h2>Todo Number: {{ todoId }}</h2>
        <p>
            やること: {{
                todoStore.todos.find((todo) => todo.id === todoId)?.title 
            }}
        </p>
        <p>
            状　　態: {{
                todoStore.todos.find((todo) => todo.id === todoId)?.completed ? '完了' : 'まだやってない'
            }}
        </p>
    </section>
</template>