<template>
  <div id="app">
    <Header @search="searching"/>

    <Main :MoviesList="MoviesList" :SeriesList="SeriesList"/>
  </div>
</template>

<script>
import axios from "axios";
import Header from './components/Header.vue';
import Main from './components/Main.vue';

export default {
  name: 'App',
  components: {
    Header,
    Main
  },
  data() {
    return {
      baseUrl: "https://api.themoviedb.org/3/search/",
      apiKey: "?api_key=3db9c7a2f859884185a1de6ddc97c03b",
      MoviesList: [],
      SeriesList: [],
    }
  },
  methods: {
    searching(text) {
      this.searchText = text;
      this.getMovie();
      this.getSerie();
    },
    getMovie() {
      axios
      .get(this.baseUrl + 'movie' + this.apiKey + "&query=" + this.searchText)
      .then((result) => {
        this.MoviesList = result.data.results;
      })
    },
    getSerie() {
      axios
      .get(this.baseUrl + 'tv' + this.apiKey + "&query=" + this.searchText)
      .then((result) => {
        this.SeriesList = result.data.results;
      })
    }
  }
}
</script>

<style lang="scss">

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: Avenir, Helvetica;
}

body {
  background-color: #111111;
}
</style>