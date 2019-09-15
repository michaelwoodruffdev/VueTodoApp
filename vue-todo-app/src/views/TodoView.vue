<template>
    <div class="todo-view">
        <h1>Todo List</h1>
        <todo-list></todo-list>
    </div>
</template>

<script>
import TodoList from '../components/TodoList.vue';

export default {
    name: 'TodoView', 
    components: {
        TodoList
    }, 
    data() {
        return {

        }
    }
}
</script>