<!-- eslint-disable vue/multi-word-component-names -->
<template>
    <div class="container mt-5">
        <div class="row g-3">
            <div v-if="loading" class="spinner-border" role="status">
                <span class="visually-hidden">Loading...</span>
            </div>
            <div v-else class="col-md-5">
                <div class="card">
                    <div class="card-header">
                        {{ post.title }}
                    </div>
                    <ul class="list-group list-group-flush">
                        <li class="list-group-item">Body : {{ post.body }}</li>
                    </ul>
                    <div class="card-footer">
                        <RouterLink class="btn btn-sm btn-danger">Delete</RouterLink>
                        <RouterLink class="btn btn-sm btn-dark ms-3" :to="{name:'editPost',params:{id:post.id}}">Edit
                        </RouterLink>
                    </div>
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
    import {
        useRoute
    } from "vue-router";
    export default {
        setup() {
            const post = ref({})
            const loading = ref(true)
            const route = useRoute()

            console.log(route.params.id)

            function getPost() {
                axios.get(`https://jsonplaceholder.typicode.com/posts/${route.params.id}`)
                    .then(function (response) {
                        post.value = response.data;
                        loading.value = false
                    })
                    .catch(function (error) {
                        console.log(error);
                    })
                    .finally(function () {});
            }
            getPost()

            return {
                post,
                loading,
                route
            }
        }
    }
</script>

<style>

</style>