<template>
  <main>
      <Card v-for="card, i in MoviesList" :key="i" :details="card"/>
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
      MoviesList: Array,
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