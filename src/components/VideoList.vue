<template>
  <ul>
    VIDEO LIST
    {{
      videos
    }}
  </ul>
</template>

<script>
export default {
  name: 'VideoList',
  props: {
    videos: {
      type: Array
    }
  }
};
</script>

<style></style>
