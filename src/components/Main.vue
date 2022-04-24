<template>
    <main>
        <div class="container">
            <section class="row p-5">
                <CardProduct v-for="(movie, index) in movies" :key="index" :movie ="movie"/>
            </section>
        </div>
    </main>
</template>

<script>
import CardProduct from './CardProduct.vue';

export default {
    name: 'MainFlix',
    components:{
        CardProduct,
    },

    data : function(){
        return {
            
        }
    },

    props: {
        movies : Array,
    },

}
</script>

<style lang='scss'>

</style>