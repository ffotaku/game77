<template>
  <div id="app">
    
    <HelloWorld msg=""/>
    <Game77 />
    
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import Game77 from "./components/Game77.vue";


export default {
  name: 'App',
  components: {
    HelloWorld,
    Game77,
  }
}
</script>

<style>
#app {
  background-image: url(https://i.imgur.com/NW0mK39.gif);
  height: 100%;
  background-size: cover;
  background-repeat: no-repeat;
  background-position: center;
  position: relative;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin: auto;
}
</style>
