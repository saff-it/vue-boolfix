<template>

  <li>

    <div class="ms_poster-container"
         v-show="active == false"
         @mouseover="getNumber()" 
    >
          <img :src="`https://image.tmdb.org/t/p/w185/${singleFilm.poster_path}`" :alt="singleFilm.title">
    </div>

    <div class="ms_text-container"
         v-show="active"
         @mouseover="getNumber()"   
    >

      <h5> <span> Titolo: </span>{{ singleFilm.title }}</h5>
      <h5> <span> Titolo Originale: </span>{{ singleFilm.original_title }}</h5>

      <p>{{ singleFilm.overview }}</p>

      <div class="ms_flag-container" v-if="singleFilm.original_language === 'en'"> 
        <img src="../assets/img/en.png" alt="uk flag">
      </div>
      <div class="ms_flag-container" v-else-if="singleFilm.original_language === 'it'">
        <img src="../assets/img/it.png" alt="it flag">
      </div>
      <div class="ms_flag-container" v-else>{{ singleFilm.original_language }}</div>

      <i v-for="index in getNumber(singleFilm.vote_average)" :key="index" class="fa-solid fa-star"></i>

    </div>

  </li>

</template>

<script>
export default {
  props: [
    'singleFilm'
  ],

  data: function() {
    return{
      active: false,
    }

  },

  methods: {
    getNumber(number) {
      return Math.round(number / 2);
    },

    setActive() {
      this.active = !this.active;
    }
  },



}
</script>

<style lang="scss" scoped>
li {
  width: calc(100% / 5 - 20px);
  margin: 0 10px 30px 10px;
  border: 2px solid red;
  background-color: black;
  cursor: pointer;

  div.ms_poster-container {
    width: 100%;

    img {
      width: 100%;
    }
  }

  div.ms_flag-container {
    width: 12%;
    display: inline-block;
    margin: 5px 5px 15px 15px;


    img {
      width: 100%;
    }
  }

  .ms_text-container{
    display: none;

    i {
      color: orange;
    }

    h5 {
      font-size: 0.8rem;
      color: white;
      margin: 5px 15px 0 15px;
      font-weight: lighter;

      span {
        font-size: 0.9rem;
        font-weight: bold;

      }
    }

    p {
      margin: 10px 15px;
      font-size: 0.8rem;
      color: rgb(114, 111, 111);
      text-align: justify;
    }
  }


}
</style>