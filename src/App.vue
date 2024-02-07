<template>
  <div>
    <Navbar />
    <BreadcumHeader title="Pago de Propinas" :cash_box="580000" />
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App" />
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import Navbar from './components/NavBar.vue';
import BreadcumHeader from './components/BreadcumHeader.vue';

export default {
  name: 'App',
  components: {
    HelloWorld,
    Navbar,
    BreadcumHeader
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;

}
</style>
