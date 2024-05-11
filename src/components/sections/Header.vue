<!-- eslint-disable vue/multi-word-component-names -->
<template>
    <header>
        <nav class="navbar navbar-expand-lg bg-body-tertiary">
            <div class="container-fluid">
                <a class="navbar-brand" href="#">WebProg.ir</a>
                <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav"
                    aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
                    <span class="navbar-toggler-icon"></span>
                </button>
                <div class="collapse navbar-collapse" id="navbarNav">
                    <ul class="navbar-nav">
                        <li class="nav-item">
                            <RouterLink class="nav-link" to="/">Home</RouterLink>
                        </li>
                        <li class="nav-item">
                            <RouterLink class="nav-link" to="/users">Users</RouterLink>
                        </li>
                        <li class="nav-item">
                            <RouterLink class="nav-link" to="/posts">Posts</RouterLink>
                        </li>
                    </ul>
                </div>
            </div>
        </nav>
    </header>
</template>

<script>
    export default {}
</script>

<style scoped>
    .router-link-active {
        color: rgba(0, 0, 0, 0.9) !important;
        border-bottom: 2px solid rgba(0, 0, 0, 0.9) !important;
    }
</style>