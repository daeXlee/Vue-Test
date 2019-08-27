<template>
  <div>
    <h1>TODO List goes here</h1>
    <div v-bind:key="todo.id" v-for="todo in todos">
        <h3>{{todo.title}}</h3>
    </div>
  </div>
</template>

<script>
export default {
  name: 'TodoList',
  props: ["todos"]
}
</script>

<style scoped>

</style>
