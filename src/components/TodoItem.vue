<template>
    <div>
        <button 
            class="todo-item" 
            v-bind:class="{'is-complete':todo.completed}" 
            @click="markCompleted"
            >{{todo.title}}
        </button>
    </div>
</template>

<script>
export default {
    name: "TodoItem",
    props: ["todo"],
    methods: {
        markCompleted() {
            this.todo.completed = !this.todo.completed
        }
    }
}
</script>

<style scoped>
    .is-complete {
        text-decoration: line-through;
    }
    .todo-item {
        background-color: lightgray;
        border-left: 5px solid green;
        line-height: 200%;
        margin-bottom: 10px;
        width: 100%;
        padding: 10px;
        font-size: 15px;
    }
</style>