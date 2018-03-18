<template>
	<ul class="menu-main">
		<li class="menu-item" v-for="item in menuItems" :key="item.id">
			<nuxt-link :to="'/' + item.path">
				{{ item.title }}
			</nuxt-link>
		</li>
	</ul>
</template>

<script>

	export default {
		data() {
			return {
				menuItems: [
					{
						id: '1',
						title: 'Home',
						path: ''
					},
					{
						id: '2',
						title: 'About',
						path: 'about'
					},
					{
						id: '3',
						title: 'Portfolio',
						path: 'portfolio'
					},
					{
						id: '4',
						title: 'Contact',
						path: 'contact'
					}
				]
			}
		}
	}

</script>

<style lang="scss" scoped>

	ul.menu-main {
		display: flex;
		flex-flow: row wrap;
		list-style: none;
		margin-left: auto;
		padding: 0;
		text-transform: uppercase;

		@include media-down(md) {
		    display: none;
		}

		li.menu-item {
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

</style>
