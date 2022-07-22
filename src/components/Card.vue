<template>
  <div>
    <div class="card">
        <h2>{{ title }}</h2>
        <h4>{{ originalTitle }}</h4>
        <p>{{ originalLanguage }}</p>
        <!-- <p class="fi-it"></p> -->
        <span>{{ vote }}</span>
    </div>
  </div>
</template>

<script>
export default {
    props: {
        title: String,
        originalTitle: String,
        originalLanguage: String,
        vote: Number,
    },
}
</script>

<style lang="scss" scoped>

</style>