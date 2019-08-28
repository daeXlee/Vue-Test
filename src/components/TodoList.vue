<template>
  <div>
    <h1>TODO List</h1>
    <div class="input-form">
        <input type="Enter Todo">
        <button>Submit</button>
    </div>
    <div v-bind:key="todo.id" v-for="todo in todos">
        <todo-item v-bind:todo="todo"/>
    </div>
  </div>
</template>

<script>
import TodoItem from './TodoItem.vue'

export default {
  name: 'TodoList',
  components: {
      TodoItem
  },
  props: ["todos"]
}
</script>

<style scoped>
    .input-form {
        margin-bottom: 10px;
        width: 100%;
    }
    input {
        /* width: 100% */
    }
</style>
