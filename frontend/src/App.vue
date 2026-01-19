<script setup lang=ts>

import { ref } from 'vue';
import AddTodo from './components/AddTodo.vue';
import { useTodoStore } from './stores/todoStore';
import { RouterView, RouterLink } from 'vue-router';

const todoStore = useTodoStore()
</script>

<template>
  <div id="app">
    <header>
      <h1>Todo App</h1>
    </header>
    <main id="main-content">
      <RouterView/>
    </main>

    <footer>
      <ul>
        <li><routerLink to="/">Home</routerLink></li>
        <li><routerLink to="/about">About</routerLink></li>
      </ul>
    </footer>
    <!-- <section class="todo-app">
    <h2>Todos</h2>
    <ul>
      <li
        v-for= "todo in todoStore.todos"
        :key= "todo.id"
        style= "display: flex; align-items: center; gap: 0.5rem; margin:0.25rem 0;"
      >
      <input type="checkbox" v-model="todo.completed" />
      <span :style="{ textDecoration: todo.completed ? 'line-through' : 'none' }">
        {{ todo.title }}
      </span>   
      <button v-on:click="todoStore.deleteTodo(todo.id)">Remove</button>
      </li>
    </ul>
  </section>

  <AddTodo/> -->

  </div>


</template>

<style scoped>
#main-content { padding: 1rem; border-style: solid; border-width:2px;}
</style>
