<template>
  <input
    type="text"
    v-bind:placeholder="placeholder"
    v-bind:value="inputValue"
    v-on:input="inputChangeHandler"
  />
  <button v-on:click="addTask">Add Task</button>

  <hr />
</template>
<script>
export default {
  props: ['inputValue', 'placeholder'],

  methods: {
    inputChangeHandler(event) {
      this.$emit('change-input-value', event);
    },
    addTask(e) {
      this.$emit('add-task', e);
    },
  },
};
</script>
