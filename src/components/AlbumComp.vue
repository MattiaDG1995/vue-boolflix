<template>
    <div>
        <h2>FILMS:</h2>
        <div class="cont d-flex  flex-direction-row">
            
            <FilmComp :arrayApi="arrayApi" v-for="(elem, index) in arrayApi" :key="index" :elem="elem"/>
            
        </div>
        <h2>SERIE:</h2>
        <div class="cont d-flex  flex-direction-row">
            <SerieComp :arrayApiSerie="arrayApiSerie" v-for="(val, index) in arrayApiSerie" :key="index" :val="val"/>
        </div>
    </div>
    
</template>

<script>

import FilmComp from './FilmComp.vue'
import SerieComp from './SerieComp.vue'

    export default {
        name: 'AlbumComp',
        props:{
            arrayApi: Array,
            arrayApiSerie: Array
        },
        components:{
            FilmComp,
            SerieComp
        }
    }
</script>

<style lang="scss" scoped>
 .cont{
    overflow: auto;
 }
</style>