<template>
    <div class="container">
        <div class="row">
            <h2 class="mb-5">Posts List:</h2>
            <div class="card col-12 mb-5" v-for="(post, index) in posts" :key="index">
                <div class="card-body">
                    <h5 class="card-title">{{post.title}}</h5>
                    <p class="card-text">{{post.content}}</p>
                    <p class="card-text">{{post.category?post.category.name:'-'}}</p>
                    <a href="#" class="btn btn-primary">Go somewhere</a>
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
                posts: []
            }
         },
         methods: {
            getPosts() {
               axios,get('/api/posts').then((response)=>{
                this.posts= response.data.results;
               });
            }
         },
         mounted(){
            this.getPost(response.data.result)
         }
     }
               
             
 </script>
 
 <style scoped lang="scss">
 
 </style>
 