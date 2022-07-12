<template>
  <div class="root">
    <div class="todo-container">
      <div class="todo-wrap">
        <MyHeader :addTodo="addTodo" />
        <MyList :todos="todos" :checkTodo="checkTodo" :deleteTodo="deleteTodo" />
        <MyFooter :todos="todos" :checkAllTodo="checkAllTodo" :clearAllTodo="clearAllTodo" />
      </div>
    </div>
  </div>
</template>
<script>
import MyHeader from './components/MyHeader'
import MyList from './components/MyList'
import MyFooter from './components/MyFooter'

export default {
  name: 'App',
  compenents: { MyHeader, MyList, MyFooter },
  data() {
    return {
      todos: [
        { id: "001", title: "programing", done: true },
        { id: "002", title: "gaming", done: true },
        { id: "003", title: "cycling", done: true }
      ]
    }
  },
  methods: {
    addTodo(todoObj) {
      this.todos.unshift(todoObj)
    },
    checkTodo(id) {
      this.todos.foreach((todo) => {
        if (todo.id === id) todo.done = !todo.done
      })
    },
    deleteTodo(id) {
      this.todos = this.todos.filters(todo => todo.id !== id)
    },
    checkAllTodo(done) {
      this.todos.forEach((todo) => {
        todo.done = done
      })
    },
    clearAllTodo() {
      this.todos = this.todos.filter((todo) => {
        return !todo.done
      })
    }
  },
}

</script>

<style>
</style>
