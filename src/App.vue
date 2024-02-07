<template>
  <div>
    <Navbar />
    <BreadcumHeader title="Pago de Propinas" :cash_box="580000" />
  
    <div class=" container-fluid">
      <div class="row">
        <div class="col">
          <!-- Contenido de la primera sección -->
          <div style="background-color: lightblue;">Sección 1</div>
          <BillSplitter/>
        </div>
        <div class="col">
          <!-- Contenido de la segunda sección -->
          <div style="background-color: lightgreen;">Sección 2</div>
        </div>
        <div class="col">
          <!-- Contenido de la tercera sección -->
          <div style="background-color: lightcoral;">Sección 3</div>
        </div>
      </div>
    </div>

    <div class="row seccion-4">
      <div class="col-12">
        <!-- Contenido de la cuarta sección -->
        <div style="background-color: lightgray;">Sección 4 (Ocupa todo el ancho)</div>
      </div>
    </div>

  </div>
</template>

<script>
import Navbar from './components/NavBar.vue';
import BreadcumHeader from './components/BreadcumHeader.vue';
import BillSplitter from '@/components/Home/BillSplitter.vue'

export default {
  name: 'App',
  components: {
    Navbar,
    BreadcumHeader,
    BillSplitter
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
  .container-fluid {
    margin-bottom: 1.3rem;
  }
  .seccion-4 {
    margin: 0.1rem;
  }
</style>
