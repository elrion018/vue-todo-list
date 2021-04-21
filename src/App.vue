<template>
  <p>Todo List</p>
  <todo-input
    :newTodoText="newTodoText"
    @update:newTodoText="updateNewTodoText"
    @submit:newTodoText="addTodo"
  ></todo-input>
  <todo-list :todos="todos" @remove:todo="removeTodo"></todo-list>
</template>

<script>
import TodoInput from './components/TodoInput.vue';
import TodoList from './components/TodoList.vue';

const createTodo = function(trimmedTodoText, todoIdCount) {
  return {
    name: trimmedTodoText,
    id: todoIdCount,
  };
};

export default {
  name: 'App',
  components: {
    TodoInput,
    TodoList,
  },

  data() {
    return {
      newTodoText: '',
      todoIdCount: 0,
      todos: [],
    };
  },

  methods: {
    addTodo() {
      const trimmedTodoText = this.newTodoText.trim();

      if (trimmedTodoText) {
        this.todos.push(createTodo(trimmedTodoText, this.todoIdCount));
      }

      this.todoIdCount += 1;
      this.newTodoText = '';
    },

    removeTodo(id) {
      const targetIndex = this.todos.findIndex(todo => todo.id === id);

      if (targetIndex !== -1) {
        this.todos.splice(targetIndex, 1);
      }
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
