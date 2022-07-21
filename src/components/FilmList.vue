<template>
  <div>
    <Card v-for="(film, index) in films" :key="index"
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