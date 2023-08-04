
<script>
import { store } from '../store';



export default{
    name :'SearchBar',
    
    setup(){
         
       

        return{store}
    }
   
}
</script>


<template>
    <div class="container ">
        <form class="d-flex justify-content-center" action="" @submit.prevent="$emit('search')">

            <input type="text" class="form-control w-auto mx-2"  placeholder="Search Charachter" v-model="store.searchtext">

            <select class="form-select w-auto mx-2" v-model="store.statusValue">
                <option selected value="">Select Status</option>
                <option value="alive">Alive</option>
                <option value="dead">Dead</option>
                <option value="unknown">Unknown</option>
            </select>

            <button class="btn btn-primary mx-2" type="submit">Ricerca</button>
            <button class="btn btn-warning mx-2" type="reset" @click="$emit('search', 'reset')">Reset</button>

        </form>
    </div>
</template>



<style lang="scss" scoped>

</style>