<template>
    <div class="bg-dark">
        <div class="container d-flex justify-content-between">
            <div>
                <h1>Boolflix</h1>
            </div>
            <div>
                <div class="input-group mb-3 search">
                <button class="btn btn-outline-secondary" type="button" id="button-addon1"><font-awesome-icon icon="fa-solid fa-magnifying-glass" /></button>
                <input type="text" class="form-control" placeholder="search..." aria-label="Example text with button addon" aria-describedby="button-addon1" v-model="inputText" @keyup="$emit('search', inputText)">
            </div>
            </div>
            
        </div>
    </div>
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
    .search{
        width: 300px;
    }

    h1{
        color: red;
    }


</style>