<template>
  <div>
    <AddTodo v-on:add-todo="addTodo"/>
    <Todos v-bind:todos='todos' v-on:del-todo="deleteTodo"/>
  </div>
</template>

<script>
import Todos from '../components/Todos.vue';
import AddTodo from '../components/AddTodo.vue';

export default {
  name: 'Home',
  components: {
    Todos,
    AddTodo
  },
  
  data() {
    return{
      todos: [
        {
          id: 1,
          title: 'Fazer uma To-do list com Vue.js',
          completed: false
        },
        {
          id: 2,
          title: 'Iniciar curso de Vue na Udemy',
          completed: false
        }
      ]
    }
  },

  methods: {
    deleteTodo(id) {
      this.todos = this.todos.filter(todo => todo.id !== id);
    },
    addTodo (newTodo) {
      this.todos = [...this.todos, newTodo]
    }
  } 
}
</script>

<style>

</style>

