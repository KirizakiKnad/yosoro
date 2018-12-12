<template>
  <div id="app">
    <img src="./assets/logo.png" alt="Logo">
    <Login/>
    <router-view/>
  </div>
</template>

<script>
import Login from "./components/login/Login"
export default {
  name: 'App',
  components: {
    Login
  }
}
</script>

<style>

</style>
