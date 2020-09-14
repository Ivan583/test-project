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