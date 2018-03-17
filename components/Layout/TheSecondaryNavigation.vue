<template>
	<div class="secondary-menu">
		<div class="toggle">
			<button @click="menuToggle = !menuToggle">toggle</button>
		</div>

		<ul class="menu" :class="{ 'is-active': menuToggle }">
			<li class="menu-item" v-for="item in menuItems" :key="item.id">
				<nuxt-link :to="'/' + item.path">
					{{ item.title }}
				</nuxt-link>
			</li>
		</ul>
	</div>
</template>

<script>
	export default {
		data() {
			return {
				menuToggle: false,
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

	.secondary-menu {
		position: relative;

		ul.menu {
			@include transition;
			padding: 0;
			list-style: none;
			position: absolute;
			top: 30px;
			right: 0;
			background-color: $color-white;
			padding: $content-padding;
			@include card-1;
			text-transform: uppercase;
			font-weight: bold;
			opacity: 0;
			transform: translateY(10px);

			&.is-active {
				opacity: 1;
				transform: none;
			}

			li.menu-item {

				a {
					text-decoration: none;
					color: $color-font;
				}
			}
		}
	}
</style>

