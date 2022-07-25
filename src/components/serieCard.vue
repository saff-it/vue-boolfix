<template>

    <li>
        <h2>Tv Series</h2>

        <div>
          <img :src="`https://image.tmdb.org/t/p/w185/${singleSerie.poster_path}`" :alt="singleSerie.title">
        </div>

        <h5>{{ singleSerie.name }}</h5>
        <h5>{{ singleSerie.original_name }}</h5>

        <h5 v-if="singleSerie.original_language === 'en'"> <img src="../assets/img/en.png" alt="uk flag"></h5>
        <h5 v-else-if="singleSerie.original_language === 'it'"> <img src="../assets/img/it.png" alt="it flag"></h5>
        <h5 v-else>{{ singleSerie.original_language }}</h5>
        
        <i v-for="index in this.getNumber(singleSerie.vote_average)" :key="index" class="fa-solid fa-star"></i>
        
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

<style lang="scss">



</style>