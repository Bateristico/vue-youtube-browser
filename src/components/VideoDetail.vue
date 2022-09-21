<template>
  <div>Video Detail: {{ video.snippet.title }}</div>
</template>

<script>
export default {
  name: 'VideoDetail',
  props: {
    video: {
      type: Object
    }
  }
};
</script>
