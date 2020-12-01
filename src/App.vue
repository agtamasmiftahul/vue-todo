<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <h3>Vue 3 Todo App</h3>
  <form>
    <label>New Todo</label>
    <input name="newTodo">
    <button>Add New Todo</button>
  </form>
</template>

<script>

export default {
  
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
