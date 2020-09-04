<template>
	<form @submit.prevent="onSubmit">
		<div class="formContent">
			<input
				v-model="text"
				class="searchBar"
				type="text"
				placeholder="Search Jokes..."
			/>
			<input class="submitButton" type="submit" value="Search Jokes" />
		</div>
	</form>
</template>

<script>
export default {
	name: 'SearchJokes',
	data() {
		return {
			text: '',
		}
	},
	methods: {
		onSubmit() {
			this.$emit('search', this.text)
			this.text = ''
		},
	},
}
</script>

<style lang="scss">
@import '@/assets/styles/mixins.scss';

.formContent {
	padding: 72px 0;
	display: grid;
	place-items: center;
}

.searchBar {
	width: 70%;
	margin-bottom: 24px;
	border-radius: 5px;
}
</style>
