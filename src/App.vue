<template>
  <div id="app">
    <Header @search="textToSearch"/>
    <Main v-for="(film, index) in searchedFilm" :key="index"
      :title="film.title"
      :originalTitle="film.original_title"
      :language="film.original_language"
      :vote="film.vote_average"/>
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
  data: function(){
    return{
      searchedFilm: [],
    }
  },
  methods: {
    textToSearch(inputSearch){
      axios.get('https://api.themoviedb.org/3/search/movie?api_key=5d52abd6795445439ccc206e6fdec146&language=it-IT&query=' + inputSearch + '&page=1&include_adult=true')
      .then((result) => {
        console.log(inputSearch);
        this.searchedFilm = result.data.results;
        console.log(this.searchedFilm);
      })
    },
  }
}
</script>

<style lang="scss" scoped>

</style>
