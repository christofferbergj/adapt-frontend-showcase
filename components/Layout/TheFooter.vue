<template>
	<footer class="footer">
		<div class="container">
			<div class="footer-logo">
				<p>Footer component</p>
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
			color: $color-white;
			text-decoration: none;
			font-weight: bold;
			@include font-size(20px);
		}
	}
</style>
