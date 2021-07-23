<template>
<div id="app">
  <searchCitizens/>
</div>
  
</template>

<script >
import HelloWorld from './components/HelloWorld.vue'
import searchCitizens from './components/searchCitizens.vue'
export default{
  name:"App",
  components:{HelloWorld,searchCitizens}
}

// This starter template is using Vue 3 experimental <script setup> SFCs
// Check out https://github.com/vuejs/rfcs/blob/master/active-rfcs/0040-script-setup.md
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
