<template>

    <li>
        
        <div class="ms_poster-container">
          <img :src="`https://image.tmdb.org/t/p/w185/${singleFilm.poster_path}`" :alt="singleFilm.title">
        </div>

        <h5>{{ singleFilm.title }}</h5>
        <h5>{{ singleFilm.original_title }}</h5>

        <div class="ms_flag-container" v-if="singleFilm.original_language === 'en'"> <img src="../assets/img/en.png" alt="uk flag"> </div>
        <div class="ms_flag-container" v-else-if="singleFilm.original_language === 'it'"> <img src="../assets/img/it.png" alt="it flag"> </div>
        <div class="ms_flag-container" v-else>{{ singleFilm.original_language }}</div>

        <i v-for="index in getNumber(singleFilm.vote_average)" :key="index" class="fa-solid fa-star"></i>

    </li>

</template>

<script>
export default {
  props: [
    'singleFilm'
  ],

  methods: {
        getNumber(number) {
            return Math.round(number / 2);
        }
    },  

}
</script>

<style lang="scss" scoped>

li{
  width: calc(100% / 6 - 20px);
  margin: 0 10px 30px 10px;
  border: 2px solid white;
  background-color: black;
  
  div.ms_poster-container{
    width: 100%;
    padding: 5px;

    img{
    width: 100%;
    }
  }

  div.ms_flag-container{
    width: 15%;
    display: inline-block;
    margin-right: 5px;

    img{
      width: 100%;
    }
  }

  i{
    color: orange;
  }
}


</style>