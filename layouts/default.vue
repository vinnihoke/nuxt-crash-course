<template>
	<div>
		<AppHeader />
		<Nuxt :class="$style.root" />
	</div>
</template>

<script>
import AppHeader from '../components/AppHeader.vue'
export default {
	components: {
		AppHeader,
	},
}
</script>

<style lang="scss" module>
@import '@/assets/styles/mixins.scss';

html {
	font-family: 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
		'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
	font-size: 16px;
	word-spacing: 1px;
	-ms-text-size-adjust: 100%;
	-webkit-text-size-adjust: 100%;
	-moz-osx-font-smoothing: grayscale;
	-webkit-font-smoothing: antialiased;
	box-sizing: border-box;
}

*,
*::before,
*::after {
	box-sizing: border-box;
	margin: 0;
}

ul,
ol,
li,
a {
	color: black;
	text-decoration: none;
	list-style: none;
}

button,
input,
select,
textarea {
	background-color: transparent; /* 1 */
	border: 1px solid WindowFrame; /* 1 */
	color: inherit; /* 1 */
	font: inherit; /* 2 */
	letter-spacing: inherit; /* 2 */
	padding: 0.25em 0.375em; /* 1 */
}

button,
input[type='submit'] {
	padding: 8px 24px;
	border-radius: 5px;
	cursor: pointer;

	&:hover {
		// border-color: lightseagreen;
		// color: lightseagreen;
		@include shadow();
	}
}

.root {
	@include container();
}
</style>
