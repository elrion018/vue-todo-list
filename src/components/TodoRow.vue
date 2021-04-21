<template>
  <li>{{ todo.name }}</li>
</template>

<script>
export default {
  setup() {},
  name: 'TodoRow',
  props: ['todo'],
};
</script>
