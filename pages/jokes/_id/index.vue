<template>
	<div>
		<div>
			<h2>{{ joke }}</h2>
			<hr />
			<small>Joke ID: {{ $route.params.id }}</small>
		</div>

		<div @click="$router.go(-1)">Go Back</div>
	</div>
</template>

<script>
import axios from 'axios'
export default {
	data() {
		return {
			joke: null,
		}
	},
	async created() {
		const config = {
			headers: {
				Accept: 'application/json',
			},
		}
		try {
			const res = await axios.get(
				`https://icanhazdadjoke.com/j/${this.$route.params.id}`,
				config
			)
			this.joke = res.data.joke
		} catch (e) {
			console.log(e.message) // eslint-disable-line no-console
		}
	},
}
</script>
