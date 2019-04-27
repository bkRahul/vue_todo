<template>
    <div class="todo-item box" v-bind:class="{'is-complete':todo.completed}">
        <h4 class="subtitle is-4">
            <input type="checkbox" v-on:change="markComplete">
            {{ todo.title }}
            <button @click="$emit('del-todo', todo.id)" class="delete del" aria-label="delete"></button>
        </h4>
  </div>
</template>

<script>
export default {
  name: 'TodoItem',
  props: ["todo"],
  methods: {
      markComplete() {
          this.todo.completed = !this.todo.completed;
      }

  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.todo-item {
    padding: 30px;
    margin: 10px;
    border-bottom: 1px solid #ccc;
}

.is-complete {
    text-decoration: line-through;
}

.delete {
    vertical-align: middle;
}
</style>
