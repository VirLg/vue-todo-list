<template>
  <Input
    v-bind:placeholder="placeholder"
    v-on:change-input-value="inputTargetValue"
    v-on:add-task="addTask"
  />

  <Task v-bind:todos="todos" v-on:delete-task="deleteTodo" />
</template>

<script>
import Input from './components/form/InputForm.vue';
import Task from './components/list/TaskList.vue';
export default {
  name: 'App',
  data() {
    return {
      todos: ['Task1', 'Task2', 'Task3'],
      placeholder: 'Ведите значение',
      inputValue: '',
    };
  },
  components: {
    Input,
    Task,
  },
  methods: {
    deleteTodo(idx) {
      this.todos.splice(idx, 1);
    },
    inputTargetValue(e) {
      this.inputValue = e.target.value;
    },
    addTask() {
      if (this.inputValue === '') {
        return;
      } else {
        this.todos.push(this.inputValue);
        this.inputValue === '';
      }
    },
  },
  watch: {},
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
</style>
