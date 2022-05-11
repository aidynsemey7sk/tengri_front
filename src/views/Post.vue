<template>
    <div class="post">
        <h1>{{post.title}}</h1>

        <img v-bind:src="post.get_image" alt="">
        <p>{{post.text}}</p>
    </div>

</template>

<script>
import axios from 'axios'
export default {
    data() {
        return {
            post: Object
        }
    },
    mounted() {
        this.getPost()
    },
    methods: {
        getPost() {
            const category_slug = this.$route.params.category_slug
            const post_slug = this.$route.params.post_slug
            console.log(category_slug, post_slug)

            axios 
                .get(`http://127.0.0.1:8000/${category_slug}/${post_slug}/`)
                .then(response => {
                    this.post = response.data
                })
                .catch(err => {
                    console.log(err)
                })
        }
    }
}

</script>

<style>
.post {
    margin-top: 350px;
    display: flex;
    flex-direction: column;
    max-width: 1200px;
}
</style>