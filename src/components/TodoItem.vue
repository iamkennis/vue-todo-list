<template>
  <div class="todo-item" v-bind:class="{'is-complete': todo.completed}">
     <p>
       <input type="checkbox" v-on:change="makeComplete">
      {{ todo.title }}
    <button @click="$emit('del-todo', todo.id)" class="del">x</button>
    </p>
  </div>
</template>

<script>
export default {
  name: "TodoItem",
  props: ["todo"],
  methods: {
    makeComplete(){
      this.todo.completed = !this.todo.completed
    },
    addTodo(){

    }
  }
}
</script>

<style scoped>
.todo-item{
  background: #f4f4f4;
  padding: 5px;
  border: 1px #cccc solid;
}

.is-complete{
  text-decoration: line-through;
}

.del{
  background: #ff0000;
  color: #fff;
  border: none;
  padding: 5px 9px;
  border-radius: 50%;
  cursor: pointer;
  float: right;
}
</style>
