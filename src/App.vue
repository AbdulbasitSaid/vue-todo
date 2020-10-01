<template>
  <div id="app">
    <Header></Header>
    <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo" />
  </div>
</template>

<script>
import Todos from "./components/Todos";
import Header from "./components/layout/Header";
export default {
  name: "App",
  methods: {
    deleteTodo(id) {
      this.todos = this.todos.filter((todo) => todo.id != id);
    },
  },
  components: {
    Todos,
    Header,
  },
  data() {
    return {
      todos: [
        { id: "1", title: "learn css", completed: false },
        { id: "2", title: "learn Vue", completed: false },
        { id: "3", title: "build an app", completed: false },
        { id: "4", title: "build more apps", completed: false },
      ],
    };
  },
};
</script>

<style lang='scss'>
* {
  margin: 0;
  padding: 0;
  box-sizing: content-box;
}
</style>
