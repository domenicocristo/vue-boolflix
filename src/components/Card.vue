<template>
  <div id="card">
    <h3>Titolo:
        <span>{{details.title}}</span>
    </h3>
    <h3>Titolo originale:
        <span>{{details.original_title}}</span>
    </h3>
    <h3>Lingua:
        <span>{{details.original_language}}</span>
    </h3>
    <h3>Voto:
        <span>{{details.vote_average}}</span>
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
#card {
    display: inline-block;
    background-color: #000;
    border: 2px solid #fff;
    margin: 10px;
    padding: 10px;
    h3 {
        color: #fff;
    }
    span {
        color: #808080;
    }
}
</style>