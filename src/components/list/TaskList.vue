<template>
  <ul>
    <li v-for="(myTodo, idx) in todos" v-bind:key="myTodo">
      <h2>{{ myTodo }}</h2>
      <button v-on:click="deleteTask(idx)">Del</button>
    </li>
  </ul>
</template>
<script>
export default {
  props: ['todos'],
  methods: {
    deleteTask(idx) {
      this.$emit('delete-task', idx);
    },
  },
};
</script>
