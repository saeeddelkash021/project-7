<!-- eslint-disable vue/multi-word-component-names -->
<template>
    <div class="container mt-5">
        <div class="row g-3">
            <div>
                <RouterLink class="btn btn-dark" :to="{ name: 'createPost' }">Create Post</RouterLink>
            </div>
            <div v-if="loading" class="spinner-border" role="status">
                <span class="visually-hidden">Loading...</span>
            </div>
            <div v-else class="col-md-4" v-for="post in posts" :key="post.id">
                <div class="card">
                    <div class="card-header">
                        <RouterLink to="{ name : 'postId ' , params :{ id : post.id } }">{{post.title}}</RouterLink>
                    </div>
                    <ul class="list-group list-group-flush">
                        <li class="list-group-item">Body : {{ post.body }}</li>
                    </ul>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    import axios from "axios";
    import {
        ref
    } from "vue";
    export default {
        setup() {
            const posts = ref([])
            const loading = ref(true)

            function getPosts() {
                axios.get("https://jsonplaceholder.typicode.com/posts")
                    .then(function (response) {
                        posts.value = response.data;
                        loading.value = false
                    })
                    .catch(function (error) {
                        console.log(error);
                    })
                    .finally(function () {});
            }
            getPosts()

            return {
                posts,
                loading,
            }
        }
    }
</script>

<style>

</style>