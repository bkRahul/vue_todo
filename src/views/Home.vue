<template>
  <div id="home">
    <AddTodo v-on:add-todo="addTodo"/>
    <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo"/>
  </div>
</template>

<script>
import Todos from '../components/Todos.vue';
import AddTodo from '../components/AddTodo.vue';




export default {
  name: 'Home',
  components: {
    Todos,
    AddTodo
  },
  data() {
    return {
      todos: []
    }
  },
  methods: {
    deleteTodo(id) {

      this.todos = this.todos.filter(todo => todo.id != id);

    },
    addTodo(newTodo) {

      this.todos = [...this.todos, newTodo];

    }
  }
}
</script>

<style>
#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.container {
  width: 50% !important;
  margin: 0 auto !important;
}
</style>
