<template>
    <div class="container form">
        <form class="level" @submit="addTodo">
            <div class="field level-left">
                <div class="control level-item">
                    <input class="input is-large" type="text" name="task" placeholder="Add Task.." v-model="title" required>
                </div>
            </div>
            <div class="field level-right">
                <div class="control level-item">
                    <button class="button is-link">Submit</button>
                </div>
            </div>    
        </form>
    </div>
</template>

<script>

 import uuid from 'uuid';

export default {
    name: "AddTodo",
    data() {
        return {
            title: ''
        }
    },
    methods: {
        addTodo(e) {
            e.preventDefault();
            const newTodo = {
                id: uuid.v4(),
                title: this.title,
                completed: false
            }
            // Send to the parent
            this.$emit('add-todo', newTodo);
            this.title = '';
            
        }
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.form {
    padding: 15px;
}
</style>
