<template>
  <input
    type="text"
    v-bind:placeholder="placeholder"
    v-bind:value="inputValue"
    v-on:input="inputChangeHandler"
  />
</template>
<script>
export default {
  props: ['inputValue', 'placeholder'],

  methods: {
    inputChangeHandler(event) {
      this.$emit('change-input-value', event);
    },
  },
};
</script>
