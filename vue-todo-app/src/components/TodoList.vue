<template>
    <div class="todo-list">
        <todo v-for="todo in todos" :key="todo.uid" :todo="todo" @removeTodo="removeTodo">

        </todo>

        <add-todo @addTodo="addTodo"></add-todo>
    </div>
</template>

<script>
import Todo from './Todo.vue';
import AddTodo from './AddTodo.vue';

export default {
    name: 'TodoList', 
    components: {
        Todo, 
        AddTodo
    }, 
    data() {
        return {
            todos: [
                {
                    title: 'Sample Todo', 
                    text: 'This is an example Todo', 
                    uid: 1
                }
            ], 
            nextUid: 2
        }
    }, 
    methods: {
        addTodo(newTodo) {
            newTodo.uid = this.nextUid;
            this.nextUid++;
            this.todos.push(newTodo);
        }, 
        removeTodo(id) {
            this.todos = this.todos.filter(todo => todo.uid !== id);
            console.log('id to delete:' + id);
            console.log('new todos array');
            console.log(this.todos);
        }
    }
}
</script>