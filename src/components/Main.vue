<template>
  <main class="main-content">
    <ul class="card°_main">
        <Character v-for="element in store.characters" :key="element" :caracter="element" />
    </ul>
  </main>
</template>

<script>
import axios from 'axios'
import Character from './Character.vue'
import store from '../store'
export default {
    components: {
        Character
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
            axios
            .get('https://db.ygoprodeck.com/api/v7/cardinfo.php')
            .then((res) =>{
                console.log(res.data.data)
                this.store.characters = res.data.data
            })
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

    



}




 
</style>