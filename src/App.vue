<template>
<div>
<input type="text" v-model="todoInput"/>
<button v-on:click="addBtnHandler">Add</button>
<ul v-for="(todo,index) in todos" :key="todo.text">
  <li><input type="checkbox" v-model="todo.checked"/> {{todo.text}}</li>
  <button v-on:click="deleteTodo(index)">Delete</button>
</ul>
</div>
</template>

<script>

export default {
  name: 'App',
  components: {

  },
  data: function() {
    return {
      todoInput:"",
      todos:[]
    }
  },
  methods: {
    addBtnHandler: function ( ) {
     console.log('hello')
     this.todos.push({text:this.todoInput,checked:false})
     this.todoInput = ""
    },
    deleteTodo: function(index) {
      this.todos.splice(index,1)
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
