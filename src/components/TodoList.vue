<template>
  <li v-for="todo in todos" :key="todo">{{ todo }}</li>
</template>

<script>
export default {
  setup() {},
  props: ['todos'],
  name: 'TodoList',
};
</script>
