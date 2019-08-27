<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" class="logo">
    <todo-list v-bind:todos="todos"/>
  </div>
</template>

<script>
import TodoList from './components/TodoList.vue'

export default {
  name: 'app',
  components: {
    TodoList
  },
  data() {
    return {
      todos: [
        {
          id: 1,
          title: "Todo 1",
          completed: false
        },
        {
          id: 2,
          title: "Todo 2",
          completed: false
        },
        {
          id: 3,
          title: "Todo 3",
          completed: false
        },
      ]
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.logo {
  height: 100px
}
</style>
