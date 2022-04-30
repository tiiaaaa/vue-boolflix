<template>
    <div class="card col-12 col-md-6 col-lg-3 mb-5 py-3 border border-3">
        <img v-if="element.poster_path" :src="`https://image.tmdb.org/t/p/w342${element.poster_path}`" class="card-img-top img-fluid" :alt="getTitle()">
        <img v-else src="https://dummyimage.com/600x400/8f878f/fff.png&text=Poster+not+avalaible" class="card-img-top img-fluid" :alt="getTitle()">
        <div class="card-body">
            <h2 class="card-title">{{getTitle()}}</h2>
            <p>{{element.overview}}</p>
            <p class="card-text m-0">Vote: {{element.vote_average}}</p>
            <p class="card-text m-0">Relase date: {{element.release_date}}</p>
            <div class="d-flex align-items-center">
                <p class="card-text m-0 me-2">Language: {{element.original_language}}</p>
                <country-flag :country="getLanguage()" size='normal'/>
            </div>

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
        },

        getLanguage(){
            switch(this.element.original_language){
                case 'en':
                    return 'gb';
                case 'ja':
                    return 'jp';
                case 'zh':
                    return 'cn';
                default:
                    return this.element.original_language;
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