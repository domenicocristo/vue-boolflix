<template>
  <div class="card">
    <div class="textCard">
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
            <span id="vote">{{Math.round(details.vote_average/2)}}</span>
            <span v-if="Math.round(details.vote_average/2) == '1'">&#9733; &#9734; &#9734; &#9734; &#9734;</span>
            <span v-else-if="Math.round(details.vote_average/2) == '2'">&#9733; &#9733; &#9734; &#9734; &#9734;</span>
            <span v-else-if="Math.round(details.vote_average/2) == '3'">&#9733; &#9733; &#9733; &#9734; &#9734;</span>
            <span v-else-if="Math.round(details.vote_average/2) == '4'">&#9733; &#9733; &#9733; &#9733; &#9734;</span>
            <span v-else-if="Math.round(details.vote_average/2) == '5'">&#9733; &#9733; &#9733; &#9733; &#9733;</span>
            <!-- <font-awesome-icon v-if="Math.round(details.vote_average/2) == '1'" icon="star" class="checked"/>
            <font-awesome-icon v-else-if="Math.round(details.vote_average/2) == '2'" icon="star" class="checked"/>
            <font-awesome-icon v-else-if="Math.round(details.vote_average/2) == '3'" icon="star" class="checked"/>
            <font-awesome-icon v-else-if="Math.round(details.vote_average/2) == '4'" icon="star" class="checked"/>
            <font-awesome-icon v-else-if="Math.round(details.vote_average/2) == '5'" icon="star" class="checked"/> -->
        </h3>
    </div>
    <img :src="'https://image.tmdb.org/t/p/w342'+details.poster_path" alt="poster">
  </div>
</template>

<script>
export default {
  name: 'CardsMovies',
  props: {
      details: Object
  }
}
</script>

<style scoped lang="scss">
.card {
    height: 515px;
    width: 344px;
    display: inline-block;
    position: relative;
    background-color: #000;
    margin: 40px;
    cursor: pointer;
    img {
        position: absolute;
        top: 0;
    }
    img:hover {
        display: none;
    }
    .textCard {
        position: absolute;
        top: 0;
        margin: 15px;
        h3 {
            position: relative;
            color: #fff;
            span {
            color: #808080;
            font-size: 17px;
            }
            img {
            height: 12px;
            width: 20px;
            position: absolute;
            top: 7px;
            left: 70px;
            }
            #vote {
            display: none;  
            }
        }
    }
}
</style>