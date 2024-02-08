<template>
    <div class="tip-history">
      <h4 class="text-align-left">Pagos</h4>
      <div class="tip-list">
        <TipCard v-for="(item, index) in history" :key="index" :item="item" />
      </div>
    </div>
  </template>
  
  <script>
  import TipCard from './TipCard.vue'; 
  
  export default {
    components: {
      TipCard
    },
    props: {
      history: {
        type: Array,
        required: true
      }
    }
  };
  </script>
  
  <style scoped>
  .tip-history {
    margin-top: 2rem;
  }
  
  .tip-list {
    overflow-y: auto;
    max-height: 22.3rem;
    margin-bottom: 1rem;
  }
  
  .tip-card {
    display: flex;
    align-items: center;
    padding: 10px;
    border-radius: 5px;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  }
  
  .tip-card i {
    font-size: 24px;
    margin-right: 10px;
  }
  
  .tip-card div {
    flex-grow: 1;
  }
  
  .tip-card p {
    margin: 0;
  }
  </style>
  