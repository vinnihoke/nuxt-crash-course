<template>
	<div>
		<h1>About Page</h1>
		<p>Let's display some corny dad jokes</p>
	</div>
</template>

<script>
export default {
	head() {
		return {
			title: 'About this App',
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
