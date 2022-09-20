<template>
  <div>
    Hi there!!!!
    <search-bar @termChange="onTermChange"></search-bar>
    <video-list :videos="videos"></video-list>
  </div>
</template>

<script>
import axios from 'axios';
import SearchBar from './components/SearchBar';
import VideoList from './components/VideoList';
const API_KEY = process.env.VUE_APP_YOUTUBE_API_KEY;

export default {
  name: 'App',
  components: { SearchBar, VideoList },
  data() {
    return {
      videos: []
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
        // console.log('youtube api response', response);
        this.videos = response.data.items;
      } catch (error) {
        console.log('Error while calling google api: ', error);
      }
    }
  }
};
</script>
