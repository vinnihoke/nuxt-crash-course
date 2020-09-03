<template>
	<div>
		<SearchJokes @search="search" />
		<Joke
			v-for="joke in jokes"
			:id="joke.id"
			:key="joke.id"
			:joke="joke.joke"
		/>
	</div>
</template>

<script>
import axios from 'axios'
import Joke from '../../components/Joke'
import SearchJokes from '../../components/SearchJokes'

export default {
	components: { Joke, SearchJokes },
	data() {
		return {
			jokes: [],
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
				'https://icanhazdadjoke.com/search',
				config
			)
			this.jokes = res.data.results
		} catch (e) {
			console.log(e.message) // eslint-disable-line no-console
		}
	},
	methods: {
		async search(value) {
			const config = {
				headers: {
					Accept: 'application/json',
				},
			}

			try {
				const res = await axios.get(
					`https://icanhazdadjoke.com/search?term=${value}`,
					config
				)
				this.jokes = res.data.results
			} catch (e) {
				console.log(e.message) // eslint-disable-line no-console
			}
		},
	},
	head() {
		return {
			title: 'Dad jokes',
			meta: [
				{
					hid: 'description',
					name: 'description',
					content: 'Best place for corny jokes',
				},
			],
		}
	},
}
</script>
