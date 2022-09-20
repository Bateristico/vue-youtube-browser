<template>
  <li class="list-group-item"><img :src="thumbnailURL" /> {{ video.snippet.title }}</li>
</template>

<script>
export default {
  name: 'VideoListItem',
  props: {
    video: {
      type: Object
    }
  },
  computed: {
    thumbnailURL() {
      return this.video.snippet.thumbnails.default.url;
    }
  }
};
</script>
