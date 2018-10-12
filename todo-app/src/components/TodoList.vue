<template>
    <div>
        <p>Completed Tasks: {{todos.filter(todo => {return todo.done === true}).length}}</p>
        <p>Pending Tasks: {{todos.filter(todo => {return todo.done === false}).length}}</p>
        <!--// we are now passing the data to the todo component to render the todo list-->
        <todo v-on:delete-todo="deleteTodo" v-on:complete-todo="completeTodo"
              v-for="todo in todos" v-bind:todo="todo" :key="todo.id"></todo>
    </div>
</template>

<script>
import Todo from './Todo';

export default {
  // name: 'TodoList',
  props: ['todos'],
  components: {
    Todo,
  },
  methods: {
    deleteTodo(todo) {
      const todoIndex = this.todos.indexOf(todo);
      this.todos.splice(todoIndex, 1);
    },
    completeTodo(todo) {
      const todoIndex = this.todos.indexOf(todo);
      this.todos[todoIndex].done = true;
    },
  },
};
</script>

<style scoped>

</style>
