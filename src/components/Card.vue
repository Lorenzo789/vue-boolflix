<template>
  <div>
    <div class="card">
        {{ title }}
        {{ originalTitle }}
        {{ originalLanguage }}
        {{ vote }}
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
    }
}
</script>

<style>

</style>