<template>
  <h1>To Do List</h1>
  <add-todo @todo-added="addTodo"/>
  <ul>
    <li v-for="item in todoItems" :key="item.id">
      <todo-item :text="item.text" :completed="item.completed" :id="item.id"/>
    </li>
  </ul>
</template>

<script>
import AddTodo from "./components/AddTodo";
import TodoItem from "./components/TodoItem";
import uniqueId from "lodash.uniqueid";
export default {
  name: 'App',
  components: {
    TodoItem,
    AddTodo
  },
  data () {
    return {
      todoItems: [
        {id: uniqueId('todo_'), text: 'Eat', completed: true},
        {id: uniqueId('todo_'), text: 'Sleep', completed: false},
        {id: uniqueId('todo_'), text: 'Read', completed: true},
        {id: uniqueId('todo_'), text: 'Work', completed: false},
      ]
    }
  },
  methods:{
    addTodo (text) {
      this.todoItems.push({id: uniqueId('todo_'), text, completed: false})
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
