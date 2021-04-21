<template>
  <form @submit.prevent="$emit('submit:newTodoText')">
    <input
      :value="newTodoText"
      @input="$emit('update:newTodoText', $event.target.value)"
    />
  </form>
</template>

<script>
export default {
  setup() {},
  name: 'TodoInput',
  props: ['newTodoText'],
  emits: ['update:newTodoText', 'submit:newTodoText'],
};
</script>
