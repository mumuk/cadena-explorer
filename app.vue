<template>
  <div>
    <NavBar/>
    <NuxtPage/>
  </div>
</template>
<style>
body {
  max-width: 1200px;
  margin: auto;
  background-color: black;
  color: white;
}
</style>
<script>
import NavBar from "./layout/NavBar";

export default {
  components: {NavBar}
}
</script>