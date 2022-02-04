<template>
	<h1>{{ title }}</h1>
	<p>Welcome!</p>
	<div v-if="showModal">
		<Modal theme="sale" @close="toggleModal">
			<h1>Some Jargon</h1>
			<p>
				Lorem, ipsum dolor sit amet consectetur
				adipisicing elit. Facilis esse molestias
				laboriosam odit laudantium, voluptas,
				aspernatur hic nam suscipit sunt corporis
				dolorum aliquam fugit voluptates? Harum ipsam
				distinctio pariatur molestias?
			</p>
			<template v-slot:links>
				<a href="">Sign Up Now!</a>
				<a href="">More Info</a>
			</template>
		</Modal>
	</div>

	<div v-if="showModal2">
		<Modal theme="" @close="toggleModal2">
			<h1>This is Modal2</h1>
			<p>
				Lorem, ipsum dolor sit amet consectetur
				adipisicing elit. Facilis esse molestias
				laboriosam odit laudantium, voluptas,
				aspernatur hic nam suscipit sunt corporis
				dolorum aliquam fugit voluptates? Harum ipsam
				distinctio pariatur molestias?
			</p>
			<template v-slot:links>
				<a href="">Sign Up Now!</a>
				<a href="">More Info</a>
			</template>
		</Modal>
	</div>
	<button @click="toggleModal">Open Modal</button>
	<button @click="toggleModal2">
		Open Modal2
	</button>
</template>

<script>
import Modal from "./components/Modal.vue";

export default {
	name: "App",
	components: { Modal },
	data() {
		return {
			title: "My First Vue App",
			header: "Sign up for the Giveaway!",
			text: "Check out cameronshadgett.com!",
			showModal: false,
			showModal2: false,
		};
	},
	methods: {
		toggleModal() {
			this.showModal = !this.showModal;
		},
		toggleModal2() {
			this.showModal2 = !this.showModal2;
		},
	},
};
</script>

<style>
#app {
	font-family: Avenir, Helvetica, Arial, sans-serif;
	-webkit-font-smoothing: antialiased;
	-moz-osx-font-smoothing: grayscale;
	text-align: center;
	color: #2c3e50;
	margin-top: 60px;
}
h1 {
	border-bottom: 1px solid #ddd;
	display: inline-block;
	padding-bottom: 10px;
}
</style>
