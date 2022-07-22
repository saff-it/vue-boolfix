<template>

    <li>
        <h5>{{ singleElement.title }}</h5>


        <h5>{{ singleElement.original_title }}</h5>

        <h5 v-if="singleElement.original_language === 'en'"> <img src="../assets/img/en.png" alt="uk flag"></h5>
        <h5 v-else-if="singleElement.original_language === 'it'"> <img src="../assets/img/it.png" alt="it flag"></h5>
        <h5 v-else>{{ singleElement.original_language }}</h5>

        <h5>{{ singleElement.vote_average }}</h5>
    </li>


</template>

<script>
export default {
  props: ['singleElement'],

}
</script>

<style>
</style>