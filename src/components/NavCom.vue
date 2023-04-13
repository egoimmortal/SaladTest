<template>
    <nav class="navbar">
		<div class="p-4 d-flex d-md-none">
			<div class="bg-dark p-4">
				<router-link to="/">START YOUR PROJECT</router-link>
				<router-link to="/about">☰</router-link>
			</div>
		</div>
		<div class="container-fluid d-none d-md-flex">
			<router-link to="/">START YOUR PROJECT</router-link>
			<div class="menu">
				<div></div>
				<div></div>
				<div></div>
			</div>
		</div>
    </nav>
</template>

<script lang="ts" setup>

</script>

<style lang="scss" scoped>
nav {
	position: relative;
	padding: 40px;
	z-index: var(--window-navbar);

	div{
		justify-content: flex-end !important;
	}

	a {
		font-weight: bold;
		color: #2c3e50;

		&.router-link-exact-active {
		color: #42b983;
		}
	}
}

.menu{
	display: flex;
    flex-direction: column;
    justify-content: space-between;

	*{
		border: solid;
		margin-top: 3px;
	}
}
</style>