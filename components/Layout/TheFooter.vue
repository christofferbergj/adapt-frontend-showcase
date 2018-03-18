<template>
	<footer class="footer">
		<div class="container">
			<div class="footer-logo">
				<nuxt-link to="/">
					<p>Footer component</p>
				</nuxt-link>
			</div>
		</div>
	</footer>
</template>

<style lang="scss" scoped>

	.footer {
		margin-top: 150px;
		background-color: $color-white;
		padding: $content-padding;

		.footer-logo {
			background: $color-primary-gradient;
			padding: 5px 10px;

			a {
				color: $color-white;
				text-decoration: none;
				font-weight: bold;
				@include font-size(20px);
			}
		}
	}
</style>
