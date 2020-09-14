<template>
  <div>
    <li>
      <span>
        <input type="checkbox" />
        <strong>{{ elem.id }}</strong>
        {{ elem.title }}
      </span>
      <button>&times;</button>
    </li>
  </div>
</template>

<script>
export default {
  props: {
    elem: {
      type: Object,
      required: true
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