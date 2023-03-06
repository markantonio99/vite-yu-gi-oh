<template>
  <main class="main-content">
    <div class="container">
       <Filter @onSearch="onSearcFn" />  
    </div>
    
    <ul class="card°_main">
        <Character v-for="element in store.characters" :key="element" :caracter="element" />
    </ul>
  </main>
</template>

<script>
import Filter from './Filter.vue'
import axios from 'axios'
import Character from './Character.vue'
import store from '../store'

export default {
    components: {
        Character,
        Filter,
    },
    data(){
        return{
            characters: [],
            store,
        }
    },
    methods: {
        fetchCharacters(){
            console.log('requires')
            const search = this.store.search
            axios
            .get(`https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0&fname=${search}`)
            .then((res) =>{
                console.log(res.data.data)
                this.store.characters = res.data.data
            })
        },
        onSearcFn(){
           console.log('ciao questa è la funzione onSearcFn')
           this.fetchCharacters()
        }
    },

    created(){
        this.fetchCharacters()
    },

}
</script>








<style lang="scss" scoped>

.main-content{
    padding: 100px 0;
    background-color: green;
    text-align: center;
    color: black;
    font-size: 20px;

    .card°_main{
        display: flex;
        flex-wrap: wrap;
        justify-content: center;
    }

    .container{
        height: 100px;
    }

 

}




 
</style>