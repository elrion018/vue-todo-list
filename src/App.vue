<template>
  <p>Todo List</p>
  <todo-input
    :newTodoText="newTodoText"
    @update:newTodoText="updateNewTodoText"
    @submit:newTodoText="addTodo"
  ></todo-input>
  <todo-list :todos="todos"></todo-list>
</template>

<script>
import TodoInput from './components/TodoInput.vue';
import TodoList from './components/TodoList.vue';

export default {
  name: 'App',
  components: {
    TodoInput,
    TodoList,
  },

  data() {
    return {
      newTodoText: '',
      todos: [],
    };
  },

  methods: {
    addTodo() {
      const trimmedTodoText = this.newTodoText.trim();

      if (trimmedTodoText) {
        this.todos.push(trimmedTodoText);
      }

      this.newTodoText = '';
    },
    updateNewTodoText($event) {
      this.newTodoText = $event;
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
