<template>
	<div class="hero">
		<h1>
			Frontend showcase - Adapt A/S
		</h1>
	</div>
</template>

<script>
	export default {
	}
</script>

<style lang="scss" scoped>

	.hero {
		width: 100%;
		background: $color-primary-gradient;
		background-size: cover;
		min-height: 300px;
		margin-bottom: $gutter;
		display: flex;
		flex-flow: row wrap;
		align-items: center;
		justify-content: center;

		@include media(md) {
			min-height: 75vh;
		}

		h1 {
			@include font-size(60px);
			color: $color-white;
			margin-bottom: 70px;

			&:first-letter {
				text-transform: uppercase;
			}
		}
	}
</style>
