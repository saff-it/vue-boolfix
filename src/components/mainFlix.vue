<template>
  <div>
    <ul>
      <filmCard  v-for="film in listFilms" :key="film.id"
            :singleFilm="film">
          
      </filmCard>
      
    </ul>


  </div>
</template>

<script>
import filmCard from './filmCard.vue'



export default {
  props: ['listFilms'],

  name: 'App',
    components: {
    filmCard,
    
  },

}
</script>

<style lang="scss">

</style>