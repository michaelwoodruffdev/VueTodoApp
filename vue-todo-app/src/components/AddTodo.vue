<template>
  <div class="add-todo">
    <input type="text" placeholder="title" v-model="newTodo.title"/>
    <input type="text" placeholder="text" v-model="newTodo.text"/>
    <button @click="addTodo()">Add Todo</button>
  </div>
</template>

<script>
export default {
    name: 'AddTodo', 
    data() {
        return {
            newTodo: {
                title: '', 
                text: ''
            }
        }
    }, 
    methods: {
        addTodo() {
            if (this.newTodo.title === '')
                return;
            this.$emit('addTodo', this.newTodo);
            this.newTodo = {
                title: '', 
                text: ''
            };
        }
    }
}
</script>

<style scoped>
.add-todo {
    background-color: #22aa22;
    padding: 10px;
    display: flex;
    justify-content: center;
}

input {
    background-color: #232323;
    border: none;
    padding: 5px;
    color: lightgrey;
    font-size: 15px;
    border-radius: 5px;
}

.add-todo > * {
    margin-left: 5px;
}

button {
    background-color: #232323;
    color: lightgrey;
    border: none;
    border-radius: 5px;
    font-size: 15px;
}

button:hover {
    background-color: grey;
    cursor: pointer;
}
</style>