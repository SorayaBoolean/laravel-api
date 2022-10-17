<template>
    <div class="container">

    </div>
     
 </template>
 
 <script>
 
     export default {
         name: 'MyMain',
         methods: {
            getPosts() {
               axios,get('/api/posts').then((response)=>{
                console.log(response)
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
 