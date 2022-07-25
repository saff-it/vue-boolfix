<template>

    <li>
        
        <div class="ms_poster-container">
          <img :src="`https://image.tmdb.org/t/p/w185/${singleSerie.poster_path}`" :alt="singleSerie.title">
        </div>

        <h5> <span> Titolo: </span>{{ singleSerie.title }}</h5>
        <h5> <span> Titolo Originale: </span>{{ singleSerie.original_title }}</h5>

        <p>{{singleSerie.overview}}</p>

        <div class="ms_flag-container" v-if="singleSerie.original_language === 'en'"> <img src="../assets/img/en.png" alt="uk flag"> </div>
        <div class="ms_flag-container" v-else-if="singleSerie.original_language === 'it'"> <img src="../assets/img/it.png" alt="it flag"> </div>
        <div class="ms_flag-container" v-else>{{ singleSerie.original_language }}</div>

        <i v-for="index in getNumber(singleSerie.vote_average)" :key="index" class="fa-solid fa-star"></i>

    </li>

</template>

<script>
export default {
  props: [
    'singleSerie'
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
  width: calc(100% / 5 - 20px);
  margin: 0 10px 30px 10px;
  border: 2px solid red;
  background-color: black;
  
  div.ms_poster-container{
    width: 100%;

    img{
    width: 100%;
    }
  }

  div.ms_flag-container{
    width: 12%;
    display: inline-block;
    margin: 5px 5px 15px 5px;


    img{
      width: 100%;
    }
  }

  i{
    color: orange;
  }

  h5{
    font-size: 0.8rem;
    color: white;
    margin: 5px 5px 0 5px;
    font-weight: lighter;

    span{
    font-size: 0.9rem;
    font-weight: bold;

    }
  }

  p{
    margin: 10px 5px;
    font-size: 0.8rem;
    color: rgb(114, 111, 111);
  }
  
}


</style>