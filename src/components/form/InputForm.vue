<template>
  <div>
    <input
      type="text"
      v-bind:placeholder="placeholder"
      v-on:input="inputChangeHandler"
    />
    <button v-on:click="addTask">Add Task</button>

    <hr />
  </div>
</template>
<script>
export default {
  props: ['placeholder'],

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
