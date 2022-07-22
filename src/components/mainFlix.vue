<template>
  <div>
    <ul>
      <filmCard  v-for="element in filmTvShowElements" :key="element.id"
                :singleElement="element"
      />    
    </ul>


  </div>
</template>

<script>
import filmCard from './filmCard.vue'



export default {
  props: [
    'filmTvShowElements',
    ],

  name: 'App',
    components: {
    filmCard,
    
  },

}
</script>

<style lang="scss">

</style>