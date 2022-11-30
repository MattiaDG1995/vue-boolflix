<template>
    <main class="p-4">
        <AlbumComp :arrayApi="arrayApi"  :arrayApiSerie="arrayApiSerie"/>
    </main>
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
    main{
        width: 100vw;
       /*  height: 100vh; */
       margin-top: 70px;
    }
</style>