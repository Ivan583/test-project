<template>
  <div>
    <ul>
      <TodoItem
        v-for="(item, i) in todo"
        :key="item.id"
        :elem="item"
        :index="i"
        @remove-elem="removeElem"
      />
    </ul>
  </div>
</template>

<script>
import TodoItem from "@/components/TodoItem";
export default {
  props: ["todo"],
  components: {
    TodoItem
  },
  methods: {
    removeElem(id) {
      this.$emit("remove-elem", id);
    }
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