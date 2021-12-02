<template>
  <div id="app">
    <Header @search="searching"/>

    <Main :MoviesList="MoviesList"/>
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
      apiUrl: "https://api.themoviedb.org/3/search/movie?api_key=3db9c7a2f859884185a1de6ddc97c03b&query=rocky",
      MoviesList: [],
      // searchText: "",
    }
  },
  created() {
    this.getMovie();
  },
  methods: {
    searching(text) {
      this.searchText = text;
    },
    getMovie() {
      axios
      .get(this.apiUrl)
      .then((result) => {
        this.MoviesList = result.data.results;
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
  background-color: #434343;
}
</style>