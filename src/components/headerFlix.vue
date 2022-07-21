<template>
  <header>
    <input v-model="inputText" type="text" placeholder="cerca" >
    <button @click="$emit('search', inputText)">Invia</button>
  </header>
</template>

<script>

export default {

  data: function () {
    return {
      inputText: '',
    }
  }


}

</script>

<style lang="scss">

</style>