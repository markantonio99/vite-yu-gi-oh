<template>
        <li class="card_item">
          <img class="tumb_main" :src="caracter.card_images[0].image_url_cropped" alt="">
          <h3 class="title_card">{{ caracter.name }}</h3>
        </li>
</template>

<script>
export default {
   props: {
    caracter: {
        type: Object,
        required: true
    }
   }
}
</script>

<style lang="scss" scoped>

.tumb_main{
    width: 40%;
    }

    .card_item{
        flex-basis: 30%;
        color: white;
    }

    .title_card{
        margin-bottom: 40px;
    }
</style>