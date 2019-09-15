<template>
    <div class="todo-list">
        <add-todo @addTodo="addTodo"></add-todo>
        <transition-group name="slide">
        <todo v-for="todo in todos" :key="todo.uid" :todo="todo" @removeTodo="removeTodo" class="todo">

        </todo>
        </transition-group>
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
        }
    }
}
</script>

<style scoped>
    .todo:nth-of-type(2n) {
        background-color: #d7d7d7;
    }

    .slide-enter-active, .slide-leave-active {
        transition: transform .2s ease, opacity .2s ease;
    }

    .slide-enter, .slide-leave-to {
        opacity: 0;
        transform: translateX(100px);
    }

    .slide-enter-to, .slide-leave {
        opacity: 1;
        transform: translateX(0px);
    }
</style>