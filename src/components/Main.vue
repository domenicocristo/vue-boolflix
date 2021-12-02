<template>
  <main>
      <Card v-for="movie, i in MoviesList" :key="i" :details="movie"/>
  </main>
</template>

<script>
import Card from './Card.vue';

export default {
  name: 'Main',
  components: {
    Card,
  },
  props: {
      MovieList: String
  }
}
</script>

<style scoped lang="scss">
main {
    padding: 30px;
}
</style>