<template>
  <div class="todo-item" v-bind:class="{'is-complete':todo.completed}">
    <p>
      <input type="checkbox" v-on:change="markComplete">
      {{todo.title}}
      <button @click="$emit('del-todo', todo.id)" class="del">Remove</button>
    </p>
  </div>
</template>

<script>
export default {
  name: "TodoItem",
  props: ["todo"],
  methods: {
      markComplete(){
          this.todo.completed = !this.todo.completed;
      }
  }
};
</script>

<style scoped>
.todo-item {
  background: #b8c5dbde;
  padding: 10px;
  border-bottom: 1px white dotted;
  border-top: 1px white solid;
  border-right: 1px white solid;
  border-left: 1px white solid;
  width: 800px;
}

.is-complete {
  text-decoration: line-through;
}

.del {
  background-color: #ff0000;
  color: #fff;
  border: none;
  padding: 5px 9px;
  cursor: pointer;
  float: right;
  margin-left: -50%;
}
</style>
