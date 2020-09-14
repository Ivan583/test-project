<template>
  <div>
    <h2>Todo application</h2>
    <router-link to="/">Home</router-link>
    <hr />
    <AddTodo @add-todo="addTodo" />
    <hr />
    <Loader v-if="loading" />
    <TodoList v-else-if="todos.length" :todo="todos" @remove-elem="removeElem" />
    <p v-else>No todos!</p>
  </div>
</template>

<script>
import TodoList from "@/components/TodoList";
import AddTodo from "@/components/AddTodo";
import Loader from "@/components/Loader";
export default {
  name: "App",
  data() {
    return {
      todos: [],
      loading: true
    };
  },
  mounted() {
    fetch("https://jsonplaceholder.typicode.com/todos?_limit=3")
      .then(response => response.json())
      .then(json => {
        setTimeout(() => {
          this.todos = json;
          this.loading = false;
        }, 2000);
      });
  },
  components: {
    TodoList,
    AddTodo,
    Loader
  },
  methods: {
    removeElem(id) {
      this.todos = this.todos.filter(t => t.id != id);
    },
    addTodo(todo) {
      this.todos.push(todo);
    }
  }
};
</script>