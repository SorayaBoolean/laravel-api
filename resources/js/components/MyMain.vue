<template>
    <div class="container">
        <div v-if="loading" class="d-flex justify-content-center ">
            <div class="spinner-grow text-primary" role="status">
                <span class="visually-hidden">Loading...</span>
            </div>
        </div>

        <div v-else class="row">
            <h2 class="mb-5">Posts List:</h2>
            <div class="card col-12 mb-5" v-for="(post, index) in posts" :key="index">
                <div class="card-body">
                    <h5 class="card-title">{{post.title}}</h5>
                    <p class="card-text">{{truncateText(post.content, 10)}}</p>
                    <p class="card-text">{{post.category?post.category.name:'-'}}</p>
                    <a href="#" class="btn btn-primary">Read post...</a>
                </div>
            </div>

        </div>
    </div>
     
 </template>
 
 <script>
 
     export default {
         name: 'MyMain',
         data () {
            return {
                posts: [],
                loading: true
            }
         },
         methods: {
            getPosts() {
               axios.get('/api/posts').then((response)=>{
                this.posts= response.data.results;
                this.loading= false;
            });
            },
            truncateText (text, maxLength) {
                if (text,length < maxLength) {
                    return text;
                }else {
                    return text.substring(0, maxLength)+ '...';
                }  
         },
         },
         mounted(){
            this.getPosts();
         },

        
     }
               
             
 </script>
 
 <style scoped lang="scss">
 
 </style>
 