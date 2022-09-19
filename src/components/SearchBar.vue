<template>
  <div>
    <input @input="onInput" />
  </div>
</template>

<style></style>

<script>
export default {
  name: 'SearchBar',
  methods: {
    onInput: function (event) {
      this.$emit('termChange', event.target.value);
    }
  }
};
</script>
