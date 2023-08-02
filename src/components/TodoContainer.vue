<template>
  <div class="section">
    <div class="container">
      <input placeholder="add new todo" v-model="newTodo" type="text" />
      <button @click.enter="create">+</button>
    </div>
    <div class="todoList">
      <TodoPage
        v-for="todo in TodoListSpisok"
        @deleted="deleteTodo"
        @checked="checkTodo"
        :key="todo.id"
        :todo="todo"
      />
    </div>
  </div>
</template>

<script>
import TodoPage from "./TodoPage";
export default {
  components: {
    TodoPage,
  },
  data() {
    return {
      newTodo: "",
      TodoListSpisok: [
        {
          id: 0,
          description: "Hello",
          isChecked: false,
        },
      ],
      nextTodoId: 1,
    };
  },
  methods: {
    create() {
      console.log("created");
      this.TodoListSpisok.push({
        id: this.nextTodoId,
        description: this.newTodo,
        isChecked: false,
      });
      this.newTodo = "";
      this.nextTodoId++;
    },
    deleteTodo(id) {
      console.log("Finish");
      const index = this.TodoListSpisok.findIndex((todo) => todo.id === id);
      this.TodoListSpisok.splice(index, 1);
    },
    checkTodo(id) {
      const index = this.TodoListSpisok.findIndex((todo) => todo.id === id);
      console.log(this.TodoListSpisok[index].isChecked);
      this.TodoListSpisok[index].isChecked = !this.TodoListSpisok[index]
        .isChecked;
    },
  },
};
</script>

<style scoped>
input {
  border-radius: 3px;
  height: 35px;
  width: 20vw;
  border: 1px rgb(14, 27, 5) solid;
  margin-right: 3px;
}
button {
  border-radius: 3px;
  height: 40px;
  width: 40px;
  color: white;
  border: 1px transparent solid;
  background-color: #47B7CB;
}
.todoList {
  margin-top: 3vh;
}
.section {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
</style>