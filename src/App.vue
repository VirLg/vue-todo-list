<template>
  <Todo v-bind:todos="todos" v-on:delete-todo="deleteTodo" />
  <Input
    v-on:click="valueInput"
    v-bind:placeholder="placeholder"
    v-bind:value="inputValue"
    v-on:change-input-value="inputTargetValue"
  />

  <h2>inputValue : {{ inputValue }}</h2>
</template>

<script>
import Todo from './components/TodoList.vue';
import Input from './components/form/InputForm.vue';
export default {
  name: 'App',
  data() {
    return {
      todos: ['Task1'],
      placeholder: 'Ведите значение',
      inputValue: '',
    };
  },
  components: {
    Todo,
    Input,
  },
  methods: {
    deleteTodo(idx) {
      this.todos.splice(idx, 1);
    },
    inputTargetValue(e) {
      this.inputValue = e.target.value;
    },
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
</style>
