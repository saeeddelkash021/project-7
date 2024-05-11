<!-- eslint-disable vue/multi-word-component-names -->
<template>
    <div class="container mt-5">
        <div class="row g-3">
            <div v-if="loading" class="spinner-border" role="status">
                <span class="visually-hidden">Loading...</span>
            </div>
            <div v-else class="col-md-4">
                <UserCardView :user="user" />
            </div>
        </div>
    </div>
</template>

<script>
    import axios from "axios";
    import {
        ref
    } from "vue";
    import UserCardView from "../../components/users/CardView.vue";
    import {
        useRouter
    } from "vue-router";
    export default {
        components: {
            UserCardView,
        },
        setup() {
            const user = ref({});
            const loading = ref(true);
            const route = useRouter();

            function getUser() {
                axios.get(`https://jsonplaceholder.typicode.com/users/${route.params.id}`)
                    .then(function (response) {
                        user.value = response.data;
                        loading.value = false
                    })
                    .catch(function (error) {
                        console.log(error);
                    })
                    .finally(function () {});
            }
            getUser()

            return {
                user,
                loading
            }
        }
    }
</script>

<style>

</style>