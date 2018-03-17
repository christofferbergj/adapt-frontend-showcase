<template>
	<header class="l-header" v-scroll-class:is-scrolled="350">
		<div class="nav">
			<div class="site-logo">
				<nuxt-link to="/">
					<p>Frontend</p>
				</nuxt-link>
			</div>

			<ul class="menu">
				<li v-for="menuItem in menuItems" :key="menuItem.id">
					<nuxt-link :to="'/' + menuItem.path">
						{{ menuItem.title }}
					</nuxt-link>
				</li>
			</ul>
		</div>
	</header>
</template>

<script>
	import VueScrollClass from 'vue-scroll-class';

	export default {
		directives: {
			'scroll-class': VueScrollClass,
		},
		data() {
			return {
				menuItems: [
					{
						title: 'Home',
						path: ''
					},
					{
						title: 'About',
						path: 'about'
					},
					{
						title: 'Portfolio',
						path: 'portfolio'
					},
					{
						title: 'Contact',
						path: 'contact'
					}
				]
			}
		}
	}
</script>

<style lang="scss" scoped>

	.l-header {
		position: fixed;
		background: $color-primary-gradient;
		width: 100%;
		padding: 30px 0;
		@include transition(.15s);

		&.is-scrolled {
			background: $color-primary-gradient;
			box-shadow: 0 2px 2px -2px rgba(0, 0, 0, .2);
			padding: 15px 0;

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

			ul {
				display: flex;
				flex-flow: row wrap;
				list-style: none;
				margin-left: auto;
				padding: 0;
				text-transform: uppercase;

				li {
					position: relative;
					@include transition;

					&:not(:first-child) {
						margin-left: 30px;
					}

					@include hover-state {

						a {
							background-color: $color-white;
							color: $color-font;
						}
					}
				;

					a {
						text-decoration: none;
						color: $color-white;
						font-weight: bold;
						padding: 5px 8px;
						@include transition;

						&.nuxt-link-exact-active {
							background-color: $color-white;
							color: $color-font;
						}
					}
				}
			}
		}
	}

</style>
