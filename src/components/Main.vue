<template>
  <main>
      <Card v-for="movie, i in results" :key="i" :details="movie"/>
  </main>
</template>

<script>
import axios from "axios";
import Card from './components/Card.vue';

export default {
  name: 'Main',
  components: {
    Card,
  },
  data() {
    return {
      apiUrl: "https://api.themoviedb.org/3/search/movie?api_key=3db9c7a2f859884185a1de6ddc97c03b&query=ritorno+al+futuro",
    }
  },
}
</script>

<style scoped lang="scss">
main {
    background-color: #434343;
}
</style>