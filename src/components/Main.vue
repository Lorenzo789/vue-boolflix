<template>
  <main>
    <div>
        {{ title }}
        {{ originalTitle }}
        {{ language }}
        {{ vote }}
    </div>
  </main>
</template>

<script>
export default {
    props: {
        title: String,
        originalTitle: String,
        language: String,
        vote: Number
    },
}
</script>

<style>

</style>