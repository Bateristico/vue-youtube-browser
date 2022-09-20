<template>
  <li>{{ video.snippet.title }}</li>
</template>

<script>
export default {
  name: 'VideoListItem',
  props: {
    video: {
      type: Object
    }
  }
};
</script>
