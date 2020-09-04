<template>
	<header class="header">
		<h1 class="title">Dad Jokes</h1>
		<ul>
			<li>
				<nuxt-link to="/jokes">
					<button>Jokes</button>
				</nuxt-link>
			</li>
			<li>
				<nuxt-link to="/about">
					<button>About</button>
				</nuxt-link>
			</li>
		</ul>
	</header>
</template>

<script>
export default {}
</script>

<style lang="scss">
.header {
	display: flex;
	justify-content: space-between;
	align-items: center;
	border-bottom: 1px solid #ccc;
	padding: 8px 16px;
}
.header .title {
	font-size: 1.5rem;
}
.header ul {
	display: flex;
}
.header li {
	margin: 0 4px;
}
</style>
