<template>
	<div>
		<div :class="$style.joke">
			<h2>{{ joke }}</h2>
			<small :class="$style.jokeId"
				>Joke ID: {{ $route.params.id }}</small
			>
			<button :class="$style.backButton" @click="$router.go(-1)">
				Go Back
			</button>
		</div>
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

<style lang="scss" module>
.joke {
	padding: 32px 24px;

	& > * {
		margin: 16px 0;
	}
}

.backButton {
	display: block;
}

.jokeId {
	color: gainsboro;
}
</style>
