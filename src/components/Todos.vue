<script setup>
import TodoItem from '../components/TodoItem.vue'
</script>
<template>
  <div v-bind:key="todo.id" v-for="todo in todos">
    <TodoItem v-bind:todo="todo" v-on:del-todo="$emit('del-todo', todo.id)"/>
  </div>
</template>

<script>
  export default {
    name: "Todos",
    props: ["todos"]
  }
</script>

<style scoped>

</style>