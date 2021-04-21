<template>
  <li>{{ todo.name }} <button @click="$emit('remove:todo')">remove</button></li>
</template>

<script>
export default {
  setup() {},
  name: 'TodoRow',
  props: ['todo'],
  emits: ['remove:todo'],
};
</script>
