<template>
  <div>
    <ul>
      <filmCard  v-for="film in listFilms" :key="film.id"
                :singleFilm="film"
      />
      
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

</style>