<template>
  <main>
      <Card v-for="movie, i in MoviesList" :key="i" :details="movie"/>
  </main>
</template>

<script>
import axios from "axios";
import Card from './Card.vue';

export default {
  name: 'Main',
  components: {
    Card,
  },
  created() {
    this.getMovie();
  },
  data() {
    return {
      apiUrl: "https://api.themoviedb.org/3/search/movie?api_key=3db9c7a2f859884185a1de6ddc97c03b&query=ritorno+al+futuro",
      MoviesList: [],
    }
  },
  methods: {
    getMovie() {
      axios
      .get(this.apiUrl)
      .then((result) => {
        this.MoviesList = result.data.results;
      })
    },
  }
}
</script>

<style scoped lang="scss">
main {
    background-color: #434343;
}
</style>