<template>
	<div class="container-fluid">
		<div class="">
			<div class="col">
				<div class="section">
					<h2>Total de propinas</h2>
					<span class="total-tip-amount">{{ formattedTotalTipAmount }}</span>
				</div>
			</div>
			<div class="col">
				<div class="section">
					<h4>Reparto entre usuarios</h4>
					<div class="row">
						<div class="col-12">
							<span class="text-bold">¿Entre cuantas personas quieres dividir las Propinas?</span>
						</div>
						<div class="col-12">
							<input type="text" v-model="tipDividedIn" class="form-control rounded-input">
							<span class="dividedbypeople">{{ dividedByPeople }}</span>
						</div>
					</div>
				</div>
			</div>
			<div class="col">
				<div class="section">
					<h4>Elige el Método de Pago</h4>
					<div class="payment-options d-flex">
						<div v-for="(option, index) in paymentOptions" :key="index"
							:class="{ 'card': true, 'selected': selectedPaymentMethod === option.value }"
							@click="selectPayment(option.value)">
							<div class="card-body">
								<i :class="option.iconClass + ' option-icon'"></i>
								<span class="option-text">{{ option.label }}</span>
							</div>
						</div>
					</div>
				</div>
			</div>
		</div>
	</div>
</template>

<script>
export default {
	data() {
		return {
			tipDividedIn: '', // Variable para almacenar los datos del input
			selectedPaymentMethod: '', // Variable para almacenar el método de pago seleccionado
			paymentOptions: [
				{ label: 'Efectivo', value: 'cash', iconClass: 'fas fa-money-bill-wave' },
				{ label: 'BBVA 4321', value: 'visa', iconClass: 'fab fa-cc-visa' },
				{ label: 'Citi 3312', value: 'mastercard', iconClass: 'fab fa-cc-mastercard' }
			]
		};
	},
	props: {
		totalTipAmount: {
			type: Number,
			default: 0 // Valor predeterminado en caso de que no se proporcione totalTipAmount
		}
	},
	methods: {
		saveData() {
			console.log('Datos ingresados:', this.tipDividedIn);
		},
		selectPayment(method) {
			this.selectedPaymentMethod = method;
			console.log('Método de pago seleccionado:', method);
		}
	},
	computed: {
		formattedTotalTipAmount() {
			// Formatea el prop totalTipAmount como moneda
			return new Intl.NumberFormat('es-ES', { style: 'currency', currency: 'EUR' }).format(this.totalTipAmount);
		},
		dividedByPeople() {
			// Calcula el valor dividido por el número de personas
			const divided = this.tipDividedIn ? this.totalTipAmount / parseInt(this.tipDividedIn) : this.totalTipAmount;
			return `$ ${divided} por persona`;
		}
	}
};
</script>

<style scoped>
.section {
	padding: 20px;
	/* Espacio interno de las secciones */
	height: 100%;
	/* Altura de las secciones */
	margin-top: 2rem;
	margin-bottom: 1rem;
}

.total-tip-amount {
	display: inline-block;
	padding: 10px 15px;
	border-radius: 10px;
	background-color: #F6DFDB; /* Cambio de color de fondo del span */
	color: #DD7160; /* Cambio de color de texto del span */
	font-weight: bold;
	
}

.dividedbypeople {
	font-weight: bold;
	margin-top: 10px;
	display: block;
}

.rounded-input {
	width: 5rem;
	/* Ancho del input */
	border-radius: 10px;
	/* Bordes redondeados */
	padding: 8px;
	/* Espacio interno */
	border: 1px solid #ced4da;
	/* Borde */
}

.form-control {
	display: inline-flex;
	margin-right: 2rem;
}

.payment-options {
	margin-top: 1rem;
}

.option-icon {
	font-size: 2.2rem;
	/* Tamaño del icono */
	margin-right: 10px;
	/* Espacio entre icono y texto */
}

.card {
	cursor: pointer;
	/* Cambio de cursor al pasar sobre la tarjeta */
	margin: 0.3rem;
	/* Espacio entre tarjetas */
	border: 1px solid #dee2e6;
	/* Borde de la tarjeta */
	border-radius: 5px;
	/* Bordes redondeados de la tarjeta */
	transition: box-shadow 0.3s ease;
	/* Transición suave para la sombra */
}

.card:hover {
	box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
	/* Sombra suave al pasar sobre la tarjeta */
}

.card-body {
	display: flex;
	/* Mostrar contenido en línea */
	align-items: center;
	/* Alinear contenido verticalmente */
	justify-content: center;
	/* Alinear contenido horizontalmente */
}

.option-text {
	text-align: center;
	/* Alinear texto al centro */
}

.selected {
	background-color: #007bff;
	/* Color de fondo de la tarjeta seleccionada */
	color: white;
	/* Color de texto de la tarjeta seleccionada */
}
</style>
