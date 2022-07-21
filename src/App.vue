<template>
  <div id="app">
    <Header @search="textToSearch"/>
    <Main />
  </div>
</template>

<script>
import Header from './components/Header.vue';
import Main from './components/Main.vue';
import axios from 'axios';

export default {
  name: 'App',
  components: {
    Header,
    Main
  },
  methods: {
    textToSearch(inputSearch){
      axios.get('https://api.themoviedb.org/3/search/movie?api_key=5d52abd6795445439ccc206e6fdec146&language=it-IT&query=' + inputSearch + '&page=1&include_adult=true')
      .then((result) => {
        console.log(result.data);
        console.log(inputSearch);
      })
    }
  }
}
</script>

<style lang="scss" scoped>

</style>
