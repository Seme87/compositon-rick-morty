
<script >

import axios from 'axios';
import { onMounted } from 'vue';
import { store } from '../store';


import SearchBar from './SearchBar.vue';
import SectionCharacters from './SectionCharacters.vue';


export default{

    components:{
        SearchBar,
        SectionCharacters
    },

    setup(){


        onMounted(()=>{
            // axios
            //   .get("https://rickandmortyapi.com/api/character")
            //   .then((resp)=>{
            //     store.posts = resp.data.results;
            //   })
            //   .catch((error) =>{
            //     console.log('errore nel recupero dati', error);
            //   })  
            searching();
        })

        const searching = (data) =>{

            if(data === 'reset'){
                store.searchtext= '';
                store.statusValue= '';
            }

            axios
              .get("https://rickandmortyapi.com/api/character", {
                params:{
                    name:store.searchtext,
                    status: store.statusValue, 
                }
              })
              .then((resp)=>{
                store.posts = resp.data.results;
              })
              .catch((error) =>{
                store.posts=[];
              }) 
        }


        
        return{store, searching}
    }
}

</script>

<template>
    <main class="py-4">
        <SearchBar @search="searching" />
        <SectionCharacters/>
    </main>
</template>

<style lang="scss" scoped>
main{
    background-color: GhostWhite;
}
</style>