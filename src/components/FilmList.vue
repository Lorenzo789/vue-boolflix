<template>
  <div>
    <Card v-for="film in films" :key="film.id"
    :title="film.title"
    :originalTitle="film.original_title"
    :originalLanguage="film.original_language"
    :vote="film.vote_average"/>
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

</style>