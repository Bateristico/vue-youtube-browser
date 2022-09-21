<template>
  <div class="container">
    <search-bar @termChange="onTermChange"></search-bar>
    <video-detail :video="selectedVideo"></video-detail>
    <video-list @videoSelect="onVideoSelect" :videos="videos"></video-list>
  </div>
</template>

<script>
import axios from 'axios';
import SearchBar from './components/SearchBar';
import VideoList from './components/VideoList';
import VideoDetail from './components/VideoDetail';

const API_KEY = process.env.VUE_APP_YOUTUBE_API_KEY;

export default {
  name: 'App',
  components: { SearchBar, VideoList, VideoDetail },
  data() {
    return {
      videos: [],
      selectedVideo: null
    };
  },
  methods: {
    async onTermChange(searchTerm) {
      try {
        const response = await axios.get('https://www.googleapis.com/youtube/v3/search', {
          params: {
            key: API_KEY,
            type: 'video',
            part: 'snippet',
            q: searchTerm
          }
        });
        this.videos = response.data.items;
        console.log('this.videos', this.videos);
      } catch (error) {
        console.log('Error while calling google api: ', error);
      }
    },
    onVideoSelect(video) {
      this.selectedVideo = video;
      return { video };
    }
  }
};
</script>
