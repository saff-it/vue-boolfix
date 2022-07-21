<template>
  <div>
    <ul>
      <li>{{films.title}}</li>
      <li>{{films.original_title}}</li>

      <li v-if="films.original_language === 'en'" > <img src="../assets/img/en.png" alt="uk flag"></li>
      <li v-else-if="films.original_language === 'it'" > <img src="../assets/img/it.png" alt="it flag"></li>
      <li v-else>{{films.original_language}}</li>

      <li>{{films.vote_average}}</li>
    </ul>


  </div>
</template>

<script>
export default {
  props: ['films'],

}
</script>

<style lang="scss">

</style>