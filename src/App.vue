<template>
  <div id="app">
    <img src="./assets/logo.png">
    <!-- <HelloWorld/> -->
    <Soga />
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld';
import Soga from './components/Soga';

export default {
  name: 'App',
  components: {
    // HelloWorld,
    Soga,
  },
};
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
