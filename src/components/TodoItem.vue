<template>
  <div class="todo-item" v-bind:class="{ completed: todo.completed }">
    <p>
      <input
        type="checkbox"
        name="completed"
        id=""
        v-on:change="markedCompleted"
      />
      {{ todo.title }}
      <button class="del" @click="$emit('del-todo', todo.id)">X</button>
    </p>
  </div>
</template>

<script>
export default {
  name: "TodoItem",
  props: ["todo"],
  methods: {
    markedCompleted() {
      this.todo.completed = !this.todo.completed;
    },
  },
};
</script>

<style lang="scss" scoped>
.del {
  background-color: red;
  color: white;
  border: none;
  margin: 4px;
  border-radius: 100%;
  height: 16px;
  width: 16px;
  float: right;
  right: 0;
  position: absolute;
}
.completed {
  text-decoration: line-through;
}
.todo-item {
  padding: 4px;
  background-color: #a1a1a1;
  border-bottom: solid 1px #0a0a0a;
  margin: 0 2px;
  p {
    font-weight: bold;
  }
}
</style>