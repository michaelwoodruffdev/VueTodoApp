<template>
  <div class="home">
    <h1>This page is just to test the vue router</h1>
    <router-link to="/todo">
      <button>go to todolist application</button>
    </router-link>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'home',
  components: {
    HelloWorld
  }
}
</script>
