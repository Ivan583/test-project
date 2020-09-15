<template>
  <div>
    <li>
      <span :class="{done: elem.completed}">
        <input type="checkbox" @change="elem.completed = !elem.completed" />
        <strong>{{ index + 1 }}</strong>
        {{ elem.title | uppercase }}
      </span>
      <button @click="$emit('remove-elem', elem.id)">&times;</button>
    </li>
  </div>
</template>

<script>
export default {
  props: {
    elem: {
      type: Object,
      required: true
    },
    index: Number
  },
  filters: {
    uppercase(value) {
      return value.toUpperCase();
    }
  }
};
</script>

<style scoped>
li {
  border: 1px solid green;
  display: flex;
  justify-content: space-between;
  padding: 0.5rem 2rem;
  margin-bottom: 1px;
}

button {
  background: red;
  color: #fff;
  font-weight: bold;
  border-radius: 50%;
}

.done {
  text-decoration: line-through;
}

input {
  margin-right: 1rem;
}
</style>