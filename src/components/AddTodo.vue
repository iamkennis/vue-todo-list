<template>
  <div>
    <form @submit="addTodo"> 
        <input type="text" v-model="title" name="title" placeholder="Add Todo...">
        <input type="submit" value="Submit" class="btn">
    </form>
  </div>
</template>

<script>
 export default{
    data(){
        return{
            title: ''
        }
    },
    methods: {
        addTodo(e){
            e.preventDefault();
            const newTodo = {
                title:this.title,
                completed: false
            }
            this.$emit('add-todo', newTodo)
        }
    }
 }
</script>

<style scoped>
form{
    display: flex;
    margin-bottom: 1rem;
}

input[type="text"]{
    flex: 10;
    padding: 5px;
}

input[type="submit"]{
    flex: 2;
}
</style>