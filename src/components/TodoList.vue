<template>
  <todo-row v-for="todo in todos" :todo="todo" :key="todo.id"></todo-row>
</template>

<script>
import TodoRow from '../components/TodoRow.vue';

export default {
  setup() {},
  name: 'TodoList',
  props: ['todos'],
  components: { TodoRow },
};
</script>
