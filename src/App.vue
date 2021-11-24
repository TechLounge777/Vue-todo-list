<template>
  <div>
    <div id="appHeader">
      <h1>Todo App</h1>
    </div>
    <TodoApp />
  </div>
</template>

<script>
import Todo from "./components/TodoApp.vue";
export default {
  components: {
    TodoApp: Todo,
  },
};
</script>

<style scoped></style>
