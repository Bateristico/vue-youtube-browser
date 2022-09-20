<template>
  <li class="list-group-item media">
    <img :src="thumbnailURL" class="mr-3" />
    <div class="media-body">{{ video.snippet.title }}</div>
  </li>
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

<style scoped>
li {
  display: flex;
  cursor: pointer;
}

li:hover {
  background-color: #eee;
}
</style>
