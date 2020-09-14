<template>
  <div>
    <ul>
      <TodoItem v-for="item in todo" :key="item.id" :elem="item" />
    </ul>
  </div>
</template>

<script>
import TodoItem from "@/components/TodoItem";
export default {
  props: ["todo"],
  components: {
    TodoItem
  }
};
</script>

<style scoped>
ul {
  list-style: none;
  margin: 0;
  padding: 0;
}
</style>