<template>
    <header class="mb-5">
        <nav class="d-flex justify-content-between align-items-center p-3">
            <div>
                <h1 class="text-danger mb-0 fw-bold ">Boolflix</h1>
            </div>

            <div class="input-group">
                <input type="text" class="form-control" placeholder="Search movie.." v-model.trim="stringToSearch">
                <button class="btn btn-danger" type="button" id="button-addon2" @click="$emit('newSearch', stringToSearch)">Search</button>
            </div>
        </nav>
    </header>
</template>

<script>
export default {
    name: 'HeaderFlix',
    data: function(){
        return{
            stringToSearch: '',
        }
    }

}
</script>

<style lang='scss' scoped>

    header{
        background-color: rgb(61, 58, 58);

        h1 {
            text-shadow: 4px 4px 10px red;
            letter-spacing: .2rem;
        }
        
        div.input-group{
        width: 30%;
    }
    }

</style>