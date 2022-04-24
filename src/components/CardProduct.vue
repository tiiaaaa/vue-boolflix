<template>
    <div class="card col-12 col-md-6 col-lg-3 mb-3">
        <img :src="`https://image.tmdb.org/t/p/w342${movie.poster_path}`" class="card-img-top img-fluid" alt="">
        <div class="card-body">
            <h4 class="card-title">{{getTitle()}}</h4>
            <p>{{movie.overview}}</p>
            <p class="card-text m-0">Vote: {{movie.vote_average}}</p>
            <p class="card-text m-0">Relase date: {{movie.release_date}}</p>
        </div>
    </div>
</template>

<script>
export default {
    name: 'CardProduct',

    props: {
        movie : Object,
    },

    methods: {
        getTitle(){
            if(this.movie.title){
                return this.movie.title;
            } else {
                return this.movie.name;
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