<template>
<div class="container-fluidtrono ">

    <section class="ms_movies">
      <h2 v-if="listFilms.length">Movies</h2>
      <ul>
        <filmCard  v-for="film in listFilms" :key="film.id"
                  :singleFilm="film"
        />
      </ul>
    </section>

    <section class="ms_series">
      <h2 v-if="listSeries.length">Series</h2>
      <ul>
        <serieCard v-for="serie in listSeries" :key="serie.id"
                  :singleSerie="serie"
        />
      </ul>
    </section>    

</div>
  
</template>

<script>
import filmCard from './filmCard.vue'
import serieCard from './serieCard.vue'



export default {
  props: [
    'listFilms',
    'listSeries',

    ],

  name: 'App',
    components: {
    filmCard,
    serieCard,
    
  },

}
</script>

<style lang="scss" scoped>

h2{
  text-align: center;
  text-transform: uppercase;
  color: red;
  font-weight: bold;
  padding: 20px 0;
}

.ms_movies ul,
.ms_series ul{
  list-style: none;
  display: flex;
  flex-wrap: wrap;
 
}

</style>