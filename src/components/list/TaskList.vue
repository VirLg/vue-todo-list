<template>
  <ul>
    <li v-for="myTodo in todos" v-bind:key="myTodo">
      <h2>{{ myTodo }}</h2>
    </li>
  </ul>
</template>
<script>
export default {
  props: ['todos'],
  methods: {},
};
</script>
