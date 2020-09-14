<template>
  <div>
    <h2>Todo application</h2>
    <AddTodo @add-todo="addTodo" />
    <hr />
    <TodoList :todo="todos" @remove-elem="removeElem" />
  </div>
</template>

<script>
import TodoList from "@/components/TodoList";
import AddTodo from "@/components/AddTodo";
export default {
  name: "App",
  data() {
    return {
      todos: []
    };
  },
  mounted() {
    fetch("https://jsonplaceholder.typicode.com/todos?_limit=3")
      .then(response => response.json())
      .then(json => {
        this.todos = json;
      });
  },
  components: {
    TodoList,
    AddTodo
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