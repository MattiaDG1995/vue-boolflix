<template>
    <div>
        <div class="cards p-2">
        <div class="card bg-dark text-white" style="width: 18rem;">
            <img :src="linkImg + val.poster_path" class="card-img-top" alt="...">
            <div class="card-body">
                <h4 class="card-title">Titolo: {{val.name}}</h4>
                <h5 class="card-title">Titolo Originale: {{val.original_name}}</h5>
                <h5 class="card-title">Lingua: {{val.original_language}}</h5>
                <img :src="linkFlag + val.original_language.toUpperCase() + '.png'">
                <p class="card-text">Voto: <font-awesome-icon icon="fa-solid fa-star" v-for="(i, index) in this.star(this.val)"  :key='index'/><font-awesome-icon icon="fa-regular fa-star" v-for="(i, index) in 5 - this.star(this.val)"  :key='index'/></p>              
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
                linkImg: 'http://image.tmdb.org/t/p/w200/',
                linkFlag: 'https://www.countryflagicons.com/SHINY/32/'
            }
        },
        beforeUpdate(){
            this.flag(this.val)
            this.star(this.val)
        },

        methods:{
            flag(val){
                if(val.original_language == 'en'){
                val.original_language = 'us'
            }else if (val.original_language === "ja") {
                val.original_language = "jp";
            } else if (val.original_language === "hi") {
                val.original_language = "in";
            } else if (val.original_language === "cs") {
                val.original_language = "cz";
            } else if (val.original_language === "ko") {
                val.original_language = "kr";
            } else if (val.original_language === "sv") {
                val.original_language = "ch";
            } else if (val.original_language === "fa") {
                val.original_language = "ir";
            } else if (val.original_language === "zh") {
                val.original_language = "cn";
            } else if (val.original_language === "he") {
                val.original_language = "il";
            } else if (val.original_language === "te") {
                val.original_language = "in";
            } else if (val.original_language === "ur") {
                val.original_language = "pk";
            } else if (val.original_language === "sq") {
                val.original_language = "al";
            } else if (val.original_language === "da") {
                val.original_language = "dk";
            } else {
                val.original_language
            
            }          
        },
        star(val){
            let stelle = parseInt(Math.round(val.vote_average)/2)
            return stelle
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