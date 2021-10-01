<template>
    <div>
        <p  v-for="post in posts" :key="post.id"><strong>Name:</strong> {{ post.name }}<br>
        <strong>Description:</strong> {{ post.description }}<br>
        <strong>Created At:</strong> {{ post.created_at}} <br>
        <strong>Updated At:</strong> {{ post.updated_at }}<br>
        </p>

         
    </div>   
        
              
</template>

<script>
    export default {
        mounted() {
            console.log("mounted");
        },
        data(){
        return {
            posts: []
        }
        },
        created(){
            axios.get('/api/posts')
            .then(res => this.posts = res.data);
        }
    }
</script>
