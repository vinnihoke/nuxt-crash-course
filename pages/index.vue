<template>
	<div class="container">
		<h2>Welcome!</h2>
		<p>
			Click the jokes page in the header to get the best corny jokes
			daily.
		</p>
	</div>
</template>

<script>
export default {
	head() {
		return {
			title: 'Welcome to dad jokes',
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
