<script>
export default{
    name:"CardCharacter",
    props:['posts'],

    setup(props){
        console.log(props.posts);
    }
    
}
</script>


<template>
    <div class="text-center">
        <img class="img-fluid rounded-circle" :src="posts.image" alt="">
        <h3 class="name mt-2 mb-3">{{posts.name}}</h3>
        <div class="status">{{ posts.status }}</div>
        <div class="species">{{ posts.species }}</div>
    </div>
</template>



<style lang="scss" scoped>

</style>