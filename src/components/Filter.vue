<template>
    <div>
    <input class="searc_filter" type="text" @keyup.enter="$event =>$emit('onSearch')" v-model="store.search" placeholder="Inserisci un termine di ricerca"> 
    </div>
  
</template>

<script>
import store from '../store'
export default {
  created () {
  },
   data(){
     return {
       
        // search: '',
        store,
  
     }
   },
   methods: {
       
        //  onEnter(){
        //     console.log('ciao bedduuu')
        //     this.$emit('onSearc')
        //  }

   }
}
</script>

<style lang="scss" scoped>

.searc_filter{
    border: 2px solid blue;
    padding: 10px;
    width: 300px;
    display: block;
    margin-left: 20px;
    
}



</style>