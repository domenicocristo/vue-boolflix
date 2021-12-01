<template>
  <div id="card">
    <h3>Titolo:
        <span>{{results.title}}</span>
    </h3>
    <h3>Titolo originale:
        <span>{{results.original_title}}</span>
    </h3>
    <h3>Lingua:
        <span>{{results.original_language}}</span>
    </h3>
    <h3>Voto:
        <span>{{results.vote_average}}</span>
    </h3>
  </div>
</template>

<script>
export default {
  name: 'Card',
  props: {
      details: Object
  }
}
</script>

<style scoped lang="scss">

</style>