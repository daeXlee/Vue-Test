<template>
  <div>
    <div v-bind:key="todo.id" v-for="todo in todos">
        <todo-item v-bind:todo="todo" v-on:delete-todo="$emit('delete-todo', todo.id)"/>
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
