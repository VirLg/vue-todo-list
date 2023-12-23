<template>
  <ul>
    <li v-for="(todo, idx) in todos" v-bind:key="todo">
      {{ todo }}
      <button v-on:click="deleteTodo(idx)">Del</button>
    </li>
  </ul>
</template>
<script>
export default {
  props: ['todos'],
  methods: {
    deleteTodo(idx) {
      this.$emit('delete-todo', idx);
    },
  },
};
</script>
