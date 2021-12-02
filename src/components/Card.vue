<template>
  <div id="card">
    <img :src="'https://image.tmdb.org/t/p/w342'+details.poster_path" alt="poster">
    <h3>Titolo: 
        <span>{{details.title}}</span>
    </h3>

    <h3>Titolo originale: 
        <span>{{details.original_title}}</span>
    </h3>

    <h3>Lingua: 
        <img v-if="details.original_language === 'it'" src="../assets/Italy.png" alt="logo">
        <img v-else-if="details.original_language === 'en'" src="../assets/United-Kingdom.png" alt="logo">
        <span v-else>{{details.original_language}}</span>

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
    width: 344px;
    display: inline-block;
    background-color: #000;
    border: 1px solid #fff;
    margin: 10px;
    cursor: pointer;
    h3 {
        color: #fff;
        span {
        color: #808080;
        font-size: 17px;
        }
        img {
            height: 12px;
            width: 20px;
        }
    }
}
</style>