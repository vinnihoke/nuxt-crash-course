<template>
	<nuxt-link :to="`jokes/${id}`">
		<div :class="$style.joke">
			<p>{{ joke }}</p>
		</div>
	</nuxt-link>
</template>

<script>
export default {
	name: 'Joke',
	props: ['joke', 'id'],
}
</script>

<style lang="scss" module>
@import '@/assets/styles/mixins.scss';

.joke {
	padding: 1rem;
	border-radius: 5px;
	border: 1px solid gainsboro;
	margin: 1rem 0;

	&:hover {
		@include shadow();
	}
}
</style>
