<template>
  <div class="todo-item" v-bind:class="{'is-complet':todo.completed} ">
    <H1>
      <input type="checkbox" v-on:change="markComplete" />
      {{todo.title}}
      <button @click="$emit('del-todo',todo.id)" class="del">x</button>
    </H1>
  </div>
</template>

<script>
export default {
  name: "TodoItem",
  props: ["todo"],
  methods: {
    markComplete() {
      this.todo.completed = !this.todo.completed;
    }
  }
};
</script>

<style scoped>
.todo-item {
  background: #f4f4f4;
  padding: 10px;
  border-bottom: 1px #cccccc dotted;
}
.is-complet {
  text-decoration: line-through;
}
.del {
  background-color: red;
  padding: 5px 9px;
  border: none;
  border-radius: 50%;
  float: right;
}
</style>