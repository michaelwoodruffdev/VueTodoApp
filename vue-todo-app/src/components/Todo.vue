<template>
  <div class="todo">
      <h1>{{ todo.title }}</h1>
      <p>{{ todo.text }}</p>
      <button @click="$emit('removeTodo', todo.uid)">X</button>
  </div>
</template>

<script>
export default {
  name: "Todo",
  props: {
    todo: Object
  }
};
</script>

<style scoped>
.todo {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    position: relative;
}

.todo:hover > button {
    opacity: 1;
}

.todo:hover {
    background-color: #cdcdcd !important;
}

.todo > * {
    margin: 0;
}

h1 {
    padding: 10px 20px;
}

p {
    padding: 0 30px 10px 30px;
}

button {
    position: absolute;
    right: 10px;
    top: 10px;
    opacity: 0;
    transition: opacity .2s ease;
    display: flex;
    align-items: center;
    justify-content: center;
    width: 40px;
    height: 40px;
    border-radius: 20px;
    background-color: #fa3333;
}

button:hover {
    background-color: red;
    cursor: pointer;
}
</style>