<template>

    <li>
        <div>
          <img :src="`https://image.tmdb.org/t/p/w185/${singleFilm.poster_path}`" :alt="singleFilm.title">
        </div>

        <h5>{{ singleFilm.title }}</h5>
        <h5>{{ singleFilm.original_title }}</h5>

        <h5 v-if="singleFilm.original_language === 'en'"> <img src="../assets/img/en.png" alt="uk flag"></h5>
        <h5 v-else-if="singleFilm.original_language === 'it'"> <img src="../assets/img/it.png" alt="it flag"></h5>
        <h5 v-else>{{ singleFilm.original_language }}</h5>

        <h5>{{ singleFilm.vote_average }}</h5>
    </li>

</template>

<script>
export default {
  props: ['singleFilm'],

}
</script>

<style>
</style>