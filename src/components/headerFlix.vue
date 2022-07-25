<template>
  <header class="container-fluid bg-dark">

    <div class="container">
      <h1>boolflix</h1>

      <div class="ms_search-tools">
        <input v-model="inputText" type="text" placeholder="cerca" >
        <button @click="$emit('search', inputText)">Invia</button>
      </div>
      
    </div>
    
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

.container{
  display: flex;
  justify-content: space-between;
  align-items: center;

  h1{
    text-transform: uppercase;
    color: red;
    font-weight: bold;
  }
}

.ms_search-tools button{
  border: none;
  color: white;
  background-color: red;
  padding: 0 10px;
  height: 30px;
}

</style>