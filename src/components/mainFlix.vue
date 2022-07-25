<template>
  <div>

    <h2 v-if="listFilms.length">Movies</h2>
    <ul>
      <filmCard  v-for="film in listFilms" :key="film.id"
                :singleFilm="film"
      />
    </ul>

    <h2 v-if="listSeries.length">Series</h2>
    <ul>
      <serieCard v-for="serie in listSeries" :key="serie.id"
                :singleSerie="serie"
      />
    </ul>

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

<style lang="scss">

ul{
  list-style: none;
  display: flex;
}

</style>