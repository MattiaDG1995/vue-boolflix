<template>
    <div>
        <AlbumComp :arrayApi="arrayApi"  :arrayApiSerie="arrayApiSerie"/>
    </div>
</template>

<script>
import AlbumComp from './AlbumComp.vue'
    export default {
        name: 'MainComp',
        props:{
            arrayApi: Array,
            arrayApiSerie: Array
        },
        components:{
            AlbumComp
        }
    }
</script>

<style lang="scss" scoped>

</style>