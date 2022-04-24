<template>
    <div class="card col-12 col-md-6 col-lg-3 mb-5 py-3 border border-3">
        <img :src="`https://image.tmdb.org/t/p/w342${element.poster_path}`" class="card-img-top img-fluid" alt="">
        <div class="card-body">
            <h2 class="card-title">{{getTitle()}}</h2>
            <p>{{element.overview}}</p>
            <p class="card-text m-0">Vote: {{element.vote_average}}</p>
            <p class="card-text m-0">Relase date: {{element.release_date}}</p>
        </div>
    </div>
</template>

<script>
export default {
    name: 'CardProduct',

    props: {
        element : Object,
    },

    methods: {
        getTitle(){
            if(this.element.title){
                return this.element.title;
            } else {
                return this.element.name;
            }
        }
    }

}
</script>

<style lang='scss' scoped>
    img{
        height: 300px;
    }

</style>