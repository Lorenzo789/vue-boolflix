<template>
  <header>
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
  </header>
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

<style>

</style>