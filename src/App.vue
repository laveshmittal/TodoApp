<template>
  <h1>ToDo App</h1>
  <TodoInput @addTodo="addTodo"></TodoInput>
  <TodoResults :todos="todos" @removeTodo="removeTodo"></TodoResults>
</template>

<script>
import TodoInput from './components/TodoInput.vue';
import TodoResults from './components/TodoResults.vue';

export default {
  name: 'App',
  components: {
    TodoInput,
    TodoResults
},
data(){
  return{
    todos:[]
  }
},
methods:{
  addTodo(todo){
    this.todos.push(todo);
  },
  removeTodo(todo){
    this.todos = this.todos.filter((t)=>t!==todo);
  }
}
}
</script>

<style >
  #app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    background-color: #27292d;
    }
  </style>