<template>
  <div id="app">
    <headerFlix @search="" />
    <mainFlix />
    
  </div>
</template>

<script>
import axios from 'axios';

import headerFlix from './components/headerFlix.vue'
import mainFlix from './components/mainFlix.vue'

export default {
  data: function() {
    return{
      dataMovies: [],
    }
  },

  name: 'App',
  components: {
    mainFlix,
    headerFlix,
  },

  methods: {
    getDataMovies() {
      axios.get('https://api.themoviedb.org/3/search/movie?api_key=76a0f6b38de7b73cfe6c7dd173889613')
        .then((result) => {
          this.dataMovies = result.data.results;
        })
        .catch((error) => {
          console.log(error);
        })
    }

    

  },

  created() {
    this.getDataMovies();
  },


}
</script>

<style lang="scss">
@import "~bootstrap/scss/bootstrap.scss";
@import "./styles/general.scss";


</style>
