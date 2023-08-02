<template>
  <div class="app">
    <h1>TodoList APP</h1>
    <TodoContainer />
  </div>
</template>

<script>
import TodoContainer from "./components/TodoContainer.vue";
export default {
  name: "App",
  components: {
    TodoContainer,
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
h1 {
  color: #47B7CB;
}
.app {
  border: 1px solid transparent;
  width: 40vw;
  margin: 0 auto;
  margin-top: 25vh;
  border-radius: 3px;
  background-color: white;
  padding-bottom: 10vh;
}
html,
body {
  width: 100%;
  height: 100%;
  background-color: #47B7CB;
}
</style>
