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