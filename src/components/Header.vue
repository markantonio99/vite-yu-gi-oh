<template>
  <header>
    <div class="container">
      <h1>{{ Title }}</h1>
    </div>
   
  </header>
</template>

<script>
export default {
   data(){
    return{
        Title: 'ciao monelli'
    }
   }
}
</script>

<style lang="scss" scoped>
  .container{
    background-color: red;
  }
</style>