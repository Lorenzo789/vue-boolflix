<template>
  <div>
    <Card v-for="tvShow in tvShows" :key="tvShow.id"
      :imageUrl="tvShow.poster_path"
      :title="tvShow.name"
      :originalTitle="tvShow.original_name"
      :originalLanguage="tvShow.original_language"
      :vote="tvShow.vote_average"/>
  </div>
</template>

<script>
import Card from './Card.vue';
export default {
    props: ["tvShows"],
    components: { Card }
}
</script>

<style>

</style>