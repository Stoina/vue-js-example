<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <MyComponent />
    {{myDataMsg}}
    <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo"/>
    <HelloWorld msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import MyComponent from './components/MyComponent.vue'
import Todos from './components/Todos'

export default {
  name: 'App',
  components: {
    HelloWorld,
    MyComponent,
    Todos
  },
  data() {
    return {
      myDataMsg: 'Hello my data',
      todos: 
      [
        {
          id: 1,
          title: "Todo one",
          completed: false
        },
        {
          id: 2,
          title: "Todo two",
          completed: true
        },
        {
          id: 3,
          title: "Todo three",
          completed: false
        }
      ]
    }
  },
  methods: {
    deleteTodo(id) {
      this.todos = this.todos.filter(x => x.id !== id);
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
