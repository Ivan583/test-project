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