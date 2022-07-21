<template>
  <div>
    <ul>
      <li>{{films.title}}</li>
      <li>{{films.original_title}}</li>
      <li>{{films.original_language}}</li>
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