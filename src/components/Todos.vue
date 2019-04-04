<template>
  <div class="container">
    <div v-bind:key="todo.id" v-for="todo in todos">
      <TodoItem v-bind:todo="todo" v-on:del-todo="$emit('del-todo', todo.id)"/>
    </div>
  </div>
</template>

<script>
import TodoItem from "./TodoItem.vue";

export default {
  name: "Todos",
  components: {
    TodoItem
  },
  props: ["todos"]
};
</script>

<style scoped>

.container {
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
}
</style>


