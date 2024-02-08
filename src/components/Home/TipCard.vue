<template>
    <div class="tip-card">
      <i :class="iconClass"></i>
      <span>{{ item.paymentMethod }}</span>
      <div class="amount">
        <span>{{ formattedAmount }}</span>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      item: {
        type: Object,
        required: true
      }
    },
    computed: {
      iconClass() {
        if (this.isCash) {
          return 'fas fa-money-bill-wave'; // Icono de efectivo
        } else if (this.isCitibank) {
          return 'fab fa-cc-mastercard'; // Icono de MasterCard para Citibank
        } else if (this.isBBVA) {
          return 'fab fa-cc-visa'; // Icono de VISA para BBVA
        } else {
          return 'fas fa-credit-card'; // Icono predeterminado
        }
      },
      formattedAmount() {
        // Formatear el monto como dinero
        return '$' + parseFloat(this.item.amount).toFixed(2);
      }
    }
  };
  </script>
  
  <style scoped>
  .tip-card {
    display: flex;
    align-items: center;
    padding: 10px;
    margin: 0.3rem 1rem 0.3rem 0rem; /* Margen en todas las direcciones */
    border-radius: 10px; /* Aumenta el radio de la esquina para el redondeado */
    border: 1px solid #ccc; /* Borde sólido y grueso */
  }
  
  .tip-card i {
    font-size: 24px;
    margin-right: 10px;
  }
  
  .tip-card div {
    flex-grow: 1;
  }
  
  .tip-card span {
    margin: 0;
  }
  
  .amount {
    text-align: right; /* Alinea el monto a la derecha */
  }
  </style>
  