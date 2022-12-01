<template>
  <div id="app" class="bg-dark">
    <div>

    </div>
    <HeaderComp @search="searchFilm"/>
    <MainComp :arrayApi="arrayApi" :arrayApiSerie="arrayApiSerie"/>
  </div>
</template>

<script>
import axios from 'axios'
import HeaderComp from './components/HeaderComp.vue'
import MainComp from './components/MainComp.vue'

export default {
  name: 'App',
  components: {
    HeaderComp,
    MainComp
  },

  data(){
    return{
        arrayApi:[],
        arrayApiSerie:[],
        searcText: '',
        apiObj:{
          link: 'https://api.themoviedb.org/3/search/',
          films:'movie',
          serieTV: 'tv',
          key:'?api_key=71b06defa52e08d758dc9a3e33d8acd5'
        },


    }
},
   mounted(){
    axios.get(`${this.apiObj.link}${this.apiObj.films}${this.apiObj.key}&query=horror`)
          .then((res)=>{
             this.arrayApi = res.data.results
              console.log(this.arrayApi)
          }),
          axios.get(`${this.apiObj.link}${this.apiObj.serieTV}${this.apiObj.key}&query=family`)
          .then((res)=>{
             this.arrayApiSerie = res.data.results
              console.log(this.arrayApiSerie)
          })

                   
  }, 

  methods: {
    searchFilm( inputText ) {
      this.searcText = inputText
      if( this.searcText !== ''){
        axios.get(`${this.apiObj.link}${this.apiObj.films}${this.apiObj.key}&query=${this.searcText}`)
          .then((res)=>{
             this.arrayApi = res.data.results
              console.log(this.arrayApi)
          }),

          axios.get(`${this.apiObj.link}${this.apiObj.serieTV}${this.apiObj.key}&query=${this.searcText}`)
          .then((res)=>{
             this.arrayApiSerie = res.data.results
              console.log(this.arrayApiSerie)
          })
      }else{
        this.arrayApi=[]
        this.arrayApiSerie=[]
      }
      
      
    },
  },
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  width: 100vw;
  height: 100vh;
  overflow-y: scroll;
  
}

*{
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}
</style>
