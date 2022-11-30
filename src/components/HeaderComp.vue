<template>
    <header>
        <div class="cont d-flex justify-content-between align-content-center">
            <div>
                <a href="https://fontmeme.com/it/font-netflix/"><img src="https://fontmeme.com/permalink/221130/8e39c74dfe76376db306b3062fc14f7d.png" alt="font-netflix" border="0"></a>
            </div>
            
            <div class="input-group p-3 search">
                <button class="btn btn-outline-secondary" type="button" id="button-addon1"><font-awesome-icon icon="fa-solid fa-magnifying-glass" /></button>
                <input type="text" class="form-control" placeholder="search..." aria-label="Example text with button addon" aria-describedby="button-addon1" v-model="inputText" @keyup="$emit('search', inputText)">
            </div>
        </div>
    </header>
</template>

<script>
    export default {
        name: 'HeaderComp',
        data(){
            return{
        inputText:" ",
        
    }
},
    }
</script>

<style lang="scss" scoped>
    header{
        z-index: 1;
        position: fixed;
        width: 100%;
        background-color: black;
    }
    .cont{
        width: 90%;
        margin: 0 auto;
        
    }
    .search{
        width: 300px;        
    }

    h1{
        color: red;
    }
</style>