<template>
  <div id="app">
    <router-link to="/">Home</router-link>
    <router-link to="/login">Login</router-link>

    <router-view msg />
  </div>
</template>

<script>
export default {
  name: "App"
};
</script>

<style>
</style>
