<template>
    <main>
        <div class="container">
            <section class="row p-5">
                <CardProduct v-for="(element, index) in moviesAndSeries" :key="index" :element ="element"/>
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
        moviesAndSeries : Array,
    },

}
</script>

<style lang='scss'>

</style>