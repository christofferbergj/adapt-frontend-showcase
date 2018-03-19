<template>
	<header class="l-header" v-scroll-class:is-scrolled="300">
		<div class="nav">
			<div class="site-logo">
				<nuxt-link to="/">
					Frontend
				</nuxt-link>
			</div>

			<TheNavigation></TheNavigation>
			<TheSecondaryNavigation></TheSecondaryNavigation>
		</div>
	</header>
</template>

<script>
	import TheNavigation from '~/components/Layout/TheNavigation';
	import TheSecondaryNavigation from '~/components/Layout/TheSecondaryNavigation';
	import VueScrollClass from 'vue-scroll-class';

	export default {
		directives: {
			'scroll-class': VueScrollClass,
		},
		components: {
			TheNavigation,
			TheSecondaryNavigation
		}
	}
</script>

<style lang="scss" scoped>

	.l-header {
		position: fixed;
		background: $color-primary-gradient;
		width: 100%;
		padding: 10px 0;
		@include transition(.15s);
		z-index: 100;

		@include media(md) {
			padding: 30px 0;
		}

		&.is-scrolled {
			background: $color-primary-gradient;
			box-shadow: 0 2px 2px -2px rgba(0, 0, 0, .2);
			padding: 5px 0;

			@include media(md) {
				padding: 15px 0;
			}

			a {
				@include font-size(15px);
			}
		}

		.nav {
			display: flex;
			flex-flow: row wrap;
			align-items: center;
			@include container;

			.site-logo {

				a {
					color: $color-white;
					text-decoration: none;
					font-weight: bold;
					@include font-size(30px);
				}
			}
		}
	}

</style>
