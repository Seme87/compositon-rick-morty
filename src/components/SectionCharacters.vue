<script>
// import axios from 'axios';
import { store } from '../store';
// import { onMounted, ref,  } from 'vue';

import CardCharacter from './CardCharacter.vue';

export default{
    name:"SectionCharacters",
    components:{
        CardCharacter,
    },
    setup(){

        // const posts = ref(null)

        
        //  onMounted(()=>{
        //     axios
        //       .get("https://rickandmortyapi.com/api/character")
        //       .then((resp)=>{
        //         posts.value = resp.data.results;
        //       })
        //       .catch((error) =>{
        //         console.log('errore nel recupero dati', error);
        //       })  
        // })

        return{store}
    },

}

</script>


<template>
    <section class="section-characters container mt-5">
        <div class="row gy-4" v-if="store.posts.length > 0">
            <CardCharacter v-for="post in store.posts" :key="store.posts.id" :posts="post" class="col-sm-6 col-md-4 col-lg-3" />
        </div>
        <div class="text-center" v-else>
            <h2>La ricerca non ha prodotto risultati!</h2>
        </div>
    </section>
</template>



<style lang="scss" scoped>

</style>