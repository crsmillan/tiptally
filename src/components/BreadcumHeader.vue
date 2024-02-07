<template>
  <div class="breadcumHeader container d-flex justify-content-between align-items-center">
    <div>
      <h4>{{ title }}</h4>
    </div>
    <div>
      <h5 v-if="cash_box">Caja: {{ formatCurrency(cash_box) }}</h5>
    </div>
  </div>
</template>
  
<script>
export default {
  props: {
    title: {
      type: String,
      required: true
    },
    cash_box: {
      type: Number,
      default: 0
    }
  },
  methods: {
    formatCurrency(value) {
      return new Intl.NumberFormat(
        'es-MX',
        {
          style: 'currency', 
          currency: 'MXN',
          minimumFractionDigits: 2,
          maximumFractionDigits: 2,
          useGrouping: true,
        }).format(value);
    }
  }
};
</script>
  
<style scoped>
.breadcumHeader {
  color: teal;
  padding: 20px;
}
</style>
  