<template>
  <h1>终于App</h1>
  <input type="text" v-model="newTodoText"/>
  <button @click="AddTodos">Add</button>
  <button @click="ClearDoneTodos">Delete done</button>
  <p v-if="todos.length === 0">There is no todos right now!</p>
  <ul v-else>
    <li v-for="todo in todos">
      <input type="checkbox" v-model="todo.isDone">
      <span v-bind:class="{isdone : todo.isDone}">{{ todo.text }}</span>
    </li>
  </ul>

</template>

<script>
export default {
  data() {
    return {
      newTodoText: "",
      todos: [
        // { isDone: Boolean, text: String }
      ],
    }
  },
  methods: {
    AddTodos() {
      if (!this.newTodoText) return alert("Make sure your todo is filled!")
      this.todos.push({
        isDone: false,
        text: this.newTodoText,
      })
      this.newTodoText = ""
    },
    ClearDoneTodos() {
      this.todos = this.todos.filter((todo) => !todo.isDone)
    },
  },
}
</script>

<style>
  .isdone {
    text-decoration: line-through;
  }
</style>