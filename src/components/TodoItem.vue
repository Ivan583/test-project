<template>
  <div>
    <li>{{ elem.title }}</li>
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