<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <h3>Vue 3 Todo App</h3>
  <form @submit.prevent="addNewTodo">
    <label>New Todo</label>
    <input v-model="newTodo" name="newTodo">
    <button>Add New Todo</button>
  </form>
  <ul>
    <li v-for="todo in todos" :key="todo.id" class="todo">
      <h3 :class="{ done: todo.done }" @click="markDone(todo)">
        {{ todo.content }}
      </h3>
    </li>
  </ul>
</template>

<script>
import { ref } from 'vue'

export default {
  setup() {
    const newTodo = ref('')
    const todos = ref([])

    function addNewTodo() {
      todos.value.push({
        id: Date.now(),
        done: false,
        content: newTodo.value
      })
      newTodo.value = ''
    }

    function markDone(todo) {
      todo.done = !todo.done
    }

    return {
      todos,
      newTodo,
      addNewTodo,
      markDone
    }
  }
}
</script>

<style>
body {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  padding-top: 1em;
  padding-bottom: 1em;
  font-size: 2em;
  width: 80%;
  margin: 0 auto;
}
input, textarea, button, p, div, section, article, select {
  display: 'block';
  width: 100%;
  font-family: sans-serif;
  font-size: 1em;
  margin: 0.5em;
}
.todo {
  cursor: pointer;
}
.done {
  text-decoration: line-through;
}
</style>
