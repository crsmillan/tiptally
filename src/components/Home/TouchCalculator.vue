<template>
    <div class="calculator">
      <!-- Input de datos -->
      <div class="input-container">
        <span class="currency-symbol">$</span>
        <input type="text" class="display" v-model="currentInput">
        <span class="clear-icon" @click="clearInput"><i class="fas fa-backspace"></i></span>
      </div>
      <!-- Botones numéricos y de confirmación -->
      <div class="buttons">
        <button v-for="button in buttons" :key="button.label" @click="handleButtonClick(button)">
          {{ button.label }}
        </button>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        currentInput: '', // Variable para almacenar la entrada del usuario
        savedValue: '', // Variable para almacenar el valor guardado
        buttons: [
          { label: '1' }, { label: '2' }, { label: '3' },
          { label: '4' }, { label: '5' }, { label: '6' },
          { label: '7' }, { label: '8' }, { label: '9' },
          { label: '0' }, { label: '00' }, { label: '✔️' } // Botón para confirmar la entrada
        ] // Botones numéricos y de confirmación
      };
    },
    methods: {
      handleButtonClick(button) {
        switch (button.label) {
          case '00':
            // Agregar doble cero
            this.currentInput += '00';
            break;
          case '✔️':
            // Confirmar la entrada y guardar el valor
            this.savedValue = this.currentInput;
            console.log('Valor guardado:', this.savedValue);
            break;
          default:
            // Agregar el valor del botón a la entrada actual
            this.currentInput += button.label;
        }
      },
      clearInput() {
        // Limpiar la entrada
        this.currentInput = this.currentInput.slice(0, -1);
      }
    }
  };
  </script>
  
  <style scoped>
  .calculator {
    width: 20rem; /* Ancho de 20 rem */
    margin: 2rem auto 0 auto; /* Margen superior de 2rem */
    border: 1px solid #ccc;
    border-radius: 5px;
    padding: 10px;
    background-color: #f9f9f9;
  }
  
  .input-container {
    position: relative;
  }
  
  .currency-symbol {
    position: absolute;
    top: 50%;
    left: 5px;
    transform: translateY(-50%);
  }
  
  .display {
    font-size: 24px;
    margin-bottom: 10px;
    padding: 5px 5px 5px 30px; /* Ajustar el padding para dar espacio al símbolo */
    width: calc(100% - 52px); /* Ajustar el ancho para compensar el icono de eliminación y el símbolo */
    text-align: right;
    border: 1px solid #ccc;
    border-radius: 3px;
    background-color: white;
  }
  
  .clear-icon {
    position: absolute;
    top: 50%;
    right: 5px;
    transform: translateY(-50%);
    cursor: pointer;
  }
  
  .clear-icon i {
    color: red;
  }
  
  .buttons {
    display: grid;
    grid-template-columns: repeat(3, 1fr); /* Tres columnas para los botones */
    grid-gap: 5px;
  }
  
  button {
    font-size: 20px;
    padding: 10px;
    border: 1px solid #ccc;
    border-radius: 3px;
    cursor: pointer;
    background-color: #fff;
  }
  
  button:hover {
    background-color: #f0f0f0;
  }
  </style>
  