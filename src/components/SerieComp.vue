<template>
    <div>
        <div class="cards p-2">
        <div class="card bg-dark text-white" style="width: 18rem;">
            <img :src="linkImg + val.poster_path" class="card-img-top" alt="...">
            <div class="card-body">
                <h4 class="card-title">Titolo: {{val.title}}</h4>
                <h5 class="card-title">Titolo Originale: {{val.original_title}}</h5>
                <h5 class="card-title">Lingua: {{val.original_language}}</h5>
                <p class="card-text">Voto: {{val.vote_average}}</p>              
            </div>
    </div>
    </div>
    </div>
</template>

<script>
    export default {
        name: 'SerieComp',
        props:{
            arrayApiSerie: Array,
            val: Object
        },
        data(){
            return{
                linkImg: 'http://image.tmdb.org/t/p/w200/'
            }
        }
    }
</script>

<style lang="scss" scoped>
.cards{
   /*  width: 300px; */
        img{
            /* aspect-ratio: 1/1; */
            object-fit: contain;
        }

        .card{
            height: 660px;
        }
}
</style>