<script setup lang=ts>
  import AddTodoForm from './AddTodoForm.vue';
  import { useTodoStore } from '../stores/todoStore';
  import { ref } from 'vue';

  const todosStore = useTodoStore();

  const newTitle = ref<string>('');
</script>

<template>
  <section>
    <h2>New Todo</h2>
    <div style="display: flex; align-items: center; gap: 0.5rem; margin-bottom: 0.25rem 0;">
      <input 
       type="text" 
       v-model="newTitle" 
       placeholder="New Todo title" 
       aria-label="New Todo title"/>
      <button v-on:click="todosStore.addTodo(newTitle)" :disabled="!newTitle">Add</button>
    </div>
  </section>
</template>
