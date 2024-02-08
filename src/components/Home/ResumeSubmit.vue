<template>
	<div class="resume-submit">
		<div class="row">
			<div class="col">
				<div class="left-title">
					<h4 style="color: #DD7160;">Total Pagado: {{ totalPaid }}</h4>
				</div>
				<div class="right-title">
					<h4>Restante por Pagar: {{ remainingToPay }}</h4>
				</div>
			</div>
			<div class="col">
				<div class="button-container">
					<button class="submit-button">Pagar ${{ totalPaid }} en Propinas</button>
				</div>
			</div>
		</div>
	</div>
</template>
  
<script>
export default {
	props: {
		totalPaid: {
			type: Number,
			default: 0 // Valor predeterminado en caso de que no se proporcione totalPaid
		},
		remainingToPay: {
			type: Number,
			default: 0 // Valor predeterminado en caso de que no se proporcione remainingToPay
		}
	}
};
</script>
  
<style scoped>
.resume-submit {
	/* Estilos del componente principal */
}

.row {
	display: flex;
	justify-content: space-between;
	align-items: center;
}

.col {
	flex-grow: 1;
}

.left-title h4,
.right-title h4 {
	margin: 0;
}

.amount {
	margin-top: 0.5rem;
	/* Ajusta según sea necesario */
	font-weight: bold;
	/* Otros estilos para el dinero */
}

.button-container {
	margin-left: 20px;
	/* Ajusta el margen según sea necesario */
}

.submit-button {
	width: 50rem;
	height: 3rem;
	border: none;
	padding: 10px 20px;
	border-radius: 50px;
	background-color: #DD7160; /* Color de fondo del botón */
	color: #fff; /* Color de texto del botón */
	font-size: 16px;
	cursor: pointer;
	transition: background-color 0.3s ease; /* Transición suave del color de fondo */
}

.submit-button:hover {
	background-color: #a0524e; /* Cambio de color de fondo al pasar el cursor sobre el botón */
}
</style>
