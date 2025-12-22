<script setup lang=ts>
    import { ref } from 'vue';
    const todos = defineModel("todos");

    const newTitle = ref('');
    const nextId= ref(Math.max(0, ...todos.value.map(todo => todo.id))+1);

    function addTodo(){
        todos.value.push({ id: nextId.value++, title: newTitle.value, completed: false });
        newTitle.value = '';
    }

</script>

<template>
    <h2>New Todo</h2>
    <div style="display: flex; align-items: center; gap: 0.5rem; margin: 0.25rem 0;">
      <input
        v-model="model.todos"
        placeholder="new Title"
        aria-label="new todo title"
      />
      <button v-on:click="addTodo" :disabled="!newTitle">Add</button>
    </div>
</template>