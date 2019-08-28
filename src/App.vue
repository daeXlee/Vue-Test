<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" class="logo">
    <Header />
    <add-todo v-on:add-todo="addTodo"/>
    <todo-list v-bind:todos="todos" v-on:delete-todo="deleteTodo"/>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import AddTodo from './components/AddTodo.vue'
import TodoList from './components/TodoList.vue'
import axios from 'axios'

export default {
  name: 'app',
  components: {
    Header,
    AddTodo,
    TodoList
  },
  data() {
    return {
      todos: []
    }
  },
  methods: {
    deleteTodo(id) {
      axios.delete(`https://jsonplaceholder.typicode.com/todos/${id}`)
        .then(res => this.todos = this.todos.filter(todo => todo.id !== id))
        .catch(err => console.log(err))
    },
    addTodo(newTodo) {
      const { title, completed} = newTodo
      
      axios.post('https://jsonplaceholder.typicode.com/todos', {
        title,
        completed,
      })
        .then(res => this.todos = [...this.todos, res.data])
        .catch(err => console.log(err))

 
    }
  },
  created() {
    axios.get('https://jsonplaceholder.typicode.com/todos?_limit=5')
      .then(res => this.todos = res.data)
      .catch(err => console.log(err))
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
