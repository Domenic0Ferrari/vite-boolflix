<script>
import axios from 'axios';
import { store } from './store';
export default {
  data() {
    return {
      store,
    }
  },
  components: {

  },
  methods: {
    RequestMoviesFromApi() {
      axios.get("https://api.themoviedb.org/3/search/movie?api_key=bfc4b1b7a0f2098e7faca48ae85e05a5&query=all").then(response => (this.store.ArrMovies = response.data.results));
    }
  },
  created() {
    axios.get("https://api.themoviedb.org/3/search/movie?api_key=bfc4b1b7a0f2098e7faca48ae85e05a5&query=all").then(response => { console.log(response.data) });
  },
}
</script>

<template></template>

<style>
* {
  font-family: Inter, system-ui, Avenir, Helvetica, Arial, sans-serif;
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
</style>
