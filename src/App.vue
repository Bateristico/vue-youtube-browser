<template>
  <div>
    Hi there!!!!
    <search-bar @termChange="onTermChange"></search-bar>
  </div>
</template>

<script>
import SearchBar from './components/SearchBar';

export default {
  name: 'App',
  components: { SearchBar },
  methods: {
    onTermChange(searchTerm) {
      console.log('parent log', searchTerm);
    }
  }
};
</script>
