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

<style scoped>
    .todo-view {
        width: 70vw;
        max-width: 800px;
        margin: auto;
        background-color: #dedede;
        border-radius: 10px;
        overflow: hidden;
        border: 2px solid #cdcdcd;
        box-shadow: 0 0 20px 0 #aaaaaaaa;
    }

    h1 {
        background-color: #23bb22;
        margin: 0;
        border: none;
        border-bottom: 2px solid #13aa11;
        text-shadow: 2px 2px lightgrey;
        font-size: 40px;
    }
</style>