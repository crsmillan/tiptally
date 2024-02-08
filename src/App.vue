<template>
  <div>
    <Navbar />
    <BreadcumHeader title="Pago de Propinas" :cash_box="580000" />
  
    <main class="container">
      <div class=" container-fluid">
        <div class="row">
          <div class="col">
            <BillSplitter/>
          </div>
          <div class="col">
            <TouchCalculator/>
          </div>
          <div class="col">
            <TipHistory :history="tips"/>
          </div>
        </div>
      </div>
  
      <div class="row seccion-4">
        <div class="col-12">
          <ResumeSubmit :totalPaid="100" :remainingToPay="30000"/>
        </div>
      </div>
    </main>
  </div>
</template>

<script>
import Navbar from './components/NavBar.vue';
import BreadcumHeader from './components/BreadcumHeader.vue';
import BillSplitter from '@/components/Home/BillSplitter.vue';
import TouchCalculator from './components/Home/TouchCalculator.vue';
import TipHistory from '@/components/Home/TipHistory.vue';
import ResumeSubmit from '@/components/Home/ResumeSubmit.vue';

export default {
  name: 'App',
  components: {
    Navbar,
    BreadcumHeader,
    BillSplitter,
    TouchCalculator,
    TipHistory, 
    ResumeSubmit
  },
  data(){
    return {
      tips: [
        { paymentMethod: 'Efectivo', amount: 10.50 },
        { paymentMethod: 'citi', amount: 10.50 },
        { paymentMethod: 'bbva 2023', amount: 10.50 },
        { paymentMethod: 'Efectivo', amount: 10.50 },
        { paymentMethod: 'Efectivo', amount: 10.50 },
        { paymentMethod: 'Efectivo', amount: 10.50 },
        { paymentMethod: 'Efectivo', amount: 10.50 },
        { paymentMethod: 'Efectivo', amount: 10.50 },
        { paymentMethod: 'Tarjeta de crédito', amount: 15.75 },
        // Otras propinas
      ]
    }
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
