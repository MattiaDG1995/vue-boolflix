<template>
    <div class="cards mx-2">      
        <img :src="linkImg + elem.poster_path" class="card-img-top" alt="...">
        <div class="card-text text-white p-2">
            <h4 class="card-title">Titolo: {{elem.title}}</h4>
            <h5 class="card-title">Titolo Originale: {{elem.original_title}}</h5>
            <h5 class="card-title">Lingua: {{elem.original_language}}</h5>
            <img :src="linkFlag + elem.original_language.toUpperCase() + '.png'">
            <p class="card-vote">Voto: <font-awesome-icon icon="fa-solid fa-star" v-for="(i, index) in this.star(this.elem)"  :key='index' /><font-awesome-icon icon="fa-regular fa-star" v-for="(i, index) in 5 - this.star(this.elem)"  :key='index'/></p>                          
        </div>       
    </div>
</template>

<script>
    export default {
        name: 'FilmComp',
        props:{
            arrayApi: Array,          
            elem: Object
        },
        data(){
            return{
                linkImg: 'http://image.tmdb.org/t/p/w500/',
                linkFlag: 'https://www.countryflagicons.com/SHINY/32/'
            }
        },

        beforeUpdate(){
            this.flag(this.elem)
            this.star(this.elem)
        },

        methods:{
            flag(elem){
                if(elem.original_language == 'en'){
                elem.original_language = 'us'
                }else if (elem.original_language === "ja") {
                    elem.original_language = "jp";
                } else if (elem.original_language === "hi") {
                    elem.original_language = "in";
                } else if (elem.original_language === "cs") {
                    elem.original_language = "cz";
                } else if (elem.original_language === "ko") {
                    elem.original_language = "kr";
                } else if (elem.original_language === "sv") {
                    elem.original_language = "ch";
                } else if (elem.original_language === "fa") {
                    elem.original_language = "ir";
                } else if (elem.original_language === "zh") {
                    elem.original_language = "cn";
                } else if (elem.original_language === "he") {
                    elem.original_language = "il";
                } else if (elem.original_language === "te") {
                    elem.original_language = "in";
                } else if (elem.original_language === "ur") {
                    elem.original_language = "pk";
                } else if (elem.original_language === "sq") {
                    elem.original_language = "al";
                } else if (elem.original_language === "da") {
                    elem.original_language = "dk";
                } else {
                    elem.original_language

                }          
        },
        
        star(elem){
            let stelle = parseInt(Math.round(elem.vote_average)/2)
            return stelle
            }
        }
    }

    
</script>

<style lang="scss" scoped>
.cards{
    background-color: black;
   height: 500px;
   aspect-ratio: 2/3;
   .card-text{
        display: none;
    }
    .card-img-top{
        width: 100%;
    }
    &:hover .card-img-top{        
        display: none;
    }
    
    &:hover .card-text{       
        display: block;
    }

    }
    .fa-star{
        color: yellow;
    }
            
</style>