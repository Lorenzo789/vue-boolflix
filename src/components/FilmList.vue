<template>
  <div>
    <h1>Films:</h1>
    <div class="wrapper">
      <Card v-for="film in films" :key="film.id"
        :imageUrl="film.poster_path"
        :title="film.title"
        :originalTitle="film.original_title"
        :originalLanguage="film.original_language"
        :vote="film.vote_average"
        :overview="film.overview"/>
    </div>
  </div>
</template>

<script>
import Card from './Card.vue';
export default {
    props: ["films"],
    components: { Card }
}
</script>

<style lang="scss" scoped>
@import'../styles/variables.scss';

  h1{
    text-align: center;
    font-size: 40px;
    color: $red;
    margin-bottom: 10px;
    text-transform: uppercase;
  }

  .wrapper{
    display: flex;
    flex-wrap: wrap;
  }

</style>