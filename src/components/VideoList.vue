<template>
  <ul class="list-group">
    <video-list-item
      v-for="video in videos"
      :key="video"
      :video="video.etag"
      @videoSelect="onVideoSelect"
    ></video-list-item>
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
  },
  methods: {
    onVideoSelect(video) {
      this.$emit('videoSelect', video);
    }
  }
};
</script>

<style></style>
