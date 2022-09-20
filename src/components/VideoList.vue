<template>
  <ul>
    <video-list-item v-for="video in videos" :key="video" :video="video.etag"></video-list-item>
  </ul>
</template>

<script>
import VideoListItem from './VideoListItem';

export default {
  name: 'VideoList',
  components: { VideoListItem },
  props: {
    videos: {
      type: Object
    }
  }
};
</script>

<style></style>
