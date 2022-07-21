<template>
  <div>
    <div>
        logo
    </div>
    <div>
        <input type="text" placeholder="Search"
            v-model="inputSearch">

        <button @click="$emit('search', inputSearch)">
            Cerca
        </button>
    </div>
  </div>
</template>

<script>
export default {
    data: function(){
        return{
            inputSearch: '',
        }
    },
}
</script>

<style lang="scss" scoped>

</style>