<template>
  <div id="app">
    <Header />
    <AddTodo v-on:add-todo="addTodo"/>
    <Todos v-bind:todos='todos' v-on:del-todo="deleteTodo"/>
  </div>
</template>

<script>
import Todos from './components/Todos.vue';
import Header from './components/Header.vue';
import AddTodo from './components/AddTodo.vue';

export default {
  name: 'App',
  components: {
    Header,
    Todos,
    AddTodo
  },
  
  data() {
    return{
      todos: [
        {
          id: 1,
          title: 'atividade 1',
          completed: false
        },
        {
          id: 2,
          title: 'ativiade 2',
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
  * {
    margin: 0;
    padding: 0;
  }

  body {
    font-family: Arial, Helvetica, sans-serif;
  }

  .btn {
    display: inline-block;
    border: none;
    background: #555;
    color: whitesmoke;
    padding: 7px 20px;
    cursor: pointer;
  }

  .btn:hover {
    background: #666;
  }
</style>
