<template>
  <div id="app">
    <mainFlix />
    <headerFlix />
  </div>
</template>

<script>
import headerFlix from './components/headerFlix.vue'
import mainFlix from './components/mainFlix.vue'

export default {
  name: 'App',
  components: {
    mainFlix,
    headerFlix,
  }
}
</script>

<style lang="scss">
@import "~bootstrap/scss/bootstrap.scss";
@import "./styles/general.scss";


</style>
