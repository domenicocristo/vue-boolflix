<template>
  <main>
      <CardsMovies v-for="movie, i in MoviesList" :key="i" :details="movie"/>

      <CardsSeries v-for="serie, i in SeriesList" :key="i" :details="serie"/>
  </main>
</template>

<script>
import CardsMovies from './CardsMovies.vue';
import CardsSeries from './CardsSeries.vue';

export default {
  name: 'Main',
  components: {
    CardsMovies,
    CardsSeries,
  },
  props: {
      MoviesList: Array,
      SeriesList: Array,
  }
}
</script>

<style scoped lang="scss">
main {
    display: flex;
    justify-content: center;
    flex-wrap: wrap;  
}
</style>