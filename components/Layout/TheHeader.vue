<template>
	<header class="l-header">
		<div class="nav" v-scroll-class:is-scrolled="450">
			<div class="container">
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
		width: 100%;
		background: linear-gradient(-90deg, #ffb88c,#de6262);
		background-size: cover;
		min-height: 300px;
		margin-bottom: $gutter;

		@include media(md) {
			min-height: 75vh;
		}

		.nav {
			position: fixed;
			width: 100%;
			padding: 30px 0;
			@include transition(.15s);

			&.is-scrolled {
				background: linear-gradient(-90deg, #ffb88c,#de6262);
				box-shadow: 0 2px 2px -2px rgba(0,0,0,.2);
				padding: 15px 0;
			}

			.container {
				display: flex;
				flex-flow: row wrap;
				align-items: center;
			}

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
					};

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
