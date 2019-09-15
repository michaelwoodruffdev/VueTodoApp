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
            this.$emit('addTodo', this.newTodo);
            this.newTodo = {
                title: '', 
                text: ''
            };
        }
    }
}
</script>