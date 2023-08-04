<script>
import { store } from '../store';
export default{
    name: 'AppFooter',
    
    setup(){



        return{store}
    }
}
</script>



<template>
    <footer class="text-center py-3 bg-dark">

        <div class="ms-number">{{ store.posts.length }}</div>
    </footer>
</template>



<style lang="scss" scoped>
footer{
    color: #fff;

    .ms-number{
        font-size: 50px;
        font-weight: bold;
    }
    
}
</style>