<script>

import axios from 'axios';

export default {
    name:'App',
    data(){
        return{
            baseUrl: 'http://127.0.0.1:8000/api/',
            posts: [],
            contentMaxLenght: 150,
            pagination:{
                current: 1,
                last: null
            }
        }
    },
    methods:{
        getApi(){
            axios.get(this.baseUrl + 'posts', {
                params:{
                    page: this.pagination.current
                }
            })
                .then(result =>{
                    this.posts = result.data.posts.data;
                    this.pagination.last = result.data.posts.last_page
                })
        }
    }
    components:{
        Header
    }
}
</script>

<template>
  
</template>

<style>

</style>