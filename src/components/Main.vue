<template>
    <main>
        <CardProduct/>
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