<template>
  <Header />

  <RouterView />
</template>

<script>
  import Header from "./components/sections/Header.vue";
  export default {
    name: 'App',
    components: {
      Header: Header
    }
  }
</script>

<style>

</style>