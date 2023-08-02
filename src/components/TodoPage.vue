<template>
  <div class="todo">
    <div class="todoText">
      <input
        :class="{ checked: todo.isChecked }"
        type="checkbox"
        @click="checkTodo"
      />
      <span :class="{ checked: todo.isChecked }" @click="checkTodo">{{
        todo.description
      }}</span>
    </div>

    <button class="delete" @click="deleteTodo">Delete</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      id: this.todo.id,
    };
  },
  props: {
    todo: {
      type: Object,
      isChecked: Boolean,
    },
  },
  methods: {
    deleteTodo() {
      this.$emit("deleted", this.todo.id);
    },
    checkTodo() {
      this.$emit("checked", this.todo.id);
    },
  },
};
</script>

<style scoped>
.delete {
  position: absolute;
  right: 3vw;
  color: white;
  background-color: red;
  border: 1px solid red;
  border-radius: 3px;
  cursor: pointer;
}
.checked {
  text-decoration: line-through;
}
.todoText {
  display: flex;
  align-items: center;
  margin-right: 5vw;
  font-weight: bold;
  cursor: pointer;
}

.todo {
  display: flex;
  position: relative;
  width: 30vw;
  margin-top: 4vh;
}
</style>