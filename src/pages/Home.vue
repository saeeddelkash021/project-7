<!-- eslint-disable vue/multi-word-component-names -->
<template>
    <div class="container mt-5">
        <div class="row">
            <div class="col-md-6">
                <p>
                    Lorem ipsum, dolor sit amet consectetur adipisicing elit. Nulla ea suscipit laboriosam officiis
                    aliquid ullam repudiandae? Distinctio nihil, ratione dignissimos sapiente laudantium obcaecati,
                    explicabo alias molestias atque necessitatibus vero quo omnis, architecto corporis error eum dolorem
                    optio incidunt et fugiat. Consectetur odio consequatur repellendus nihil recusandae autem nam,
                    dolore est lorem imsum
                </p>

                <RouterLink class="btn btn-dark" :to="{name:'users'}">Users</RouterLink>
                <RouterLink class="btn btn-danger ms-2" :to="{name:'posts'}">Posts</RouterLink>
            </div>
        </div>
    </div>
</template>

<script>
    export default {

    }
</script>

<style>

</style>