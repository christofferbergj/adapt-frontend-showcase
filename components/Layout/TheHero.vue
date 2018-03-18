<template>
	<div class="hero">
		<h1 v-if="$route.path == '/'">
			Frontend showcase - Adapt A/S
		</h1>

		<h1 v-else>
			Hello from the <span>{{ $route.name }}</span> view
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
		margin-bottom: $gutter-small;
		display: flex;
		flex-flow: row wrap;
		align-items: center;
		justify-content: center;
		padding: $content-padding;

		@include media(md) {
			min-height: 75vh;
		}

		h1 {
			color: $color-white;

			@include media(md) {
				@include font-size(45px);
				margin-bottom: 70px;
			}

			@include media(lg) {
				@include font-size(60px);
			}

			span {
				position: relative;

				&:after {
					content:"";
					border-bottom: 3px solid #fff;
					position: absolute;
					bottom: -10px;
					left: 0;
					right: 0;
					margin: 0 auto;
					width: 100px;
				}
			}
		}
	}
</style>

<script>
	export default {
		data() {
			return {
				isFront: false,
			}
		},
	}
</script>
