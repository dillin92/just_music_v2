<template>
 <div id="app" class="h-screen bg-gray-100 overflow-hidden">
    <router-view :key="$route.path"/>
  </div>
</template>

<script>

export default {
  name: 'App',

  
 
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
