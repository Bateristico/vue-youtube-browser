<template>
  <div>
    Hi there!!!!
    <search-bar @termChange="onTermChange"></search-bar>
  </div>
</template>

<script>
import axios from 'axios';
import SearchBar from './components/SearchBar';
const API_KEY = process.env.VUE_APP_YOUTUBE_API_KEY;

export default {
  name: 'App',
  components: { SearchBar },
  methods: {
    async onTermChange(searchTerm) {
      try {
        const response = await axios.get('https://googleapis.com/youtube/v3/search', {
          params: {
            key: API_KEY,
            type: 'video',
            part: 'snippet',
            q: searchTerm
          }
        });

        console.log('youtube api response', response);
      } catch (error) {
        console.log('Error while calling google api: ', error);
      }
    }
  }
};
</script>
