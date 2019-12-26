<template>
  <div class="todo-item">
    <h1>{{todo.title}}</h1>
  </div>
</template>

<script>
export default {
  name: "TodoItem",
  props: ["todo"]
};
</script>

<style>
.todo-item {
  background: #f4f4f4;
  padding: 10px;
  border-bottom: 1px #cccccc dotted;
}
</style>