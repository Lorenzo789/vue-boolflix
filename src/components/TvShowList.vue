<template>
  <div>
    <h1>Serie</h1>
    <div class="wrapper-show">
      <Card v-for="tvShow in tvShows" :key="tvShow.id"
        :imageUrl="tvShow.poster_path"
        :title="tvShow.name"
        :originalTitle="tvShow.original_name"
        :originalLanguage="tvShow.original_language"
        :vote="tvShow.vote_average"
        :overview="tvShow.overview"/>
    </div>
  </div>
</template>

<script>
import Card from './Card.vue';
export default {
    props: ["tvShows"],
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
  }
  .wrapper-show{
    display: flex;
    flex-wrap: wrap;

  }
</style>