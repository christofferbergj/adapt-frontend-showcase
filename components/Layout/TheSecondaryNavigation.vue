<template>
	<div class="menu-secondary">
		<div class="menu-toggle-wrapper" @click="toggleMenu">
			<div class="menu-toggle" :class="{ 'is-active': menuIsActive }" >
				<div class="line-menu top"></div>
				<div class="line-menu middle"></div>
				<div class="line-menu bottom"></div>
			</div>
		</div>

		<ul class="menu" :class="{ 'is-active': menuIsActive }" v-click-outside="hideMenu">
			<li class="menu-item" v-for="item in menuItems" :key="item.id" @click="hideMenu">
				<nuxt-link :to="'/' + item.path">
					{{ item.title }}
				</nuxt-link>
			</li>
		</ul>
	</div>
</template>

<script>
	import ClickOutside from 'vue-click-outside';

	export default {
		directives: {
			ClickOutside
		},
		data() {
			return {
				menuIsActive: false,
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
		},
		mounted () {
			// prevent click outside event with popupItem.
			this.popupItem = this.$el
		},
		methods: {
			toggleMenu() {
				this.menuIsActive = !this.menuIsActive;
			},
			hideMenu() {
				this.menuIsActive = false
			}
		}
	}
</script>

<style lang="scss" scoped>

	.menu-secondary {
		position: relative;

		@include media-down(md) {
		    display: none;
		}

		.menu-toggle-wrapper {
			padding: 5px;
			cursor: pointer;
		}

		.menu-toggle {
			width: 30px;
			height: 20px;
			display: flex;
			flex-direction: column;
			justify-content: space-between;
			cursor: pointer;
			@include transition();
			margin-left: 50px;

			.line-menu {
				background-color: $color-white;
				width: 100%;
				height: 3px;
				@include transition();

				&.middle {
					width: 65%;
				}
			}

			&.is-active {

				.line-menu {
					margin-left: 5px;

					&.top {
						transform: rotate(45deg) translateY(12px);
						transition-delay: .1s;
					}

					&.middle {
						opacity: 0;
					}

					&.bottom {
						transform: rotate(-45deg) translateY(-12px);
						transition-delay: .1s;
					}
				}
			}
		}

		ul.menu {
			@include transition;
			padding: 0;
			list-style: none;
			position: absolute;
			top: 53px;
			right: 0;
			background-color: $color-white;
			padding: 10px 30px;
			@include card-1;
			text-transform: uppercase;
			font-weight: bold;
			opacity: 0;
			transform: translateY(10px);
			min-width: 300px;
			transition-delay: .1s;
			pointer-events: none;

			&.is-active {
				opacity: 1;
				transform: none;
				pointer-events: auto;
			}

			li.menu-item {
				margin: 15px 0;
				display: flex;
				flex-flow: row wrap;

				a {
					width: 100%;
					padding: 5px;
					text-decoration: none;
					color: $color-font;
					@include transition;

					@include hover-state {
						color: $color-primary;
					};
				}
			}
		}
	}
</style>

