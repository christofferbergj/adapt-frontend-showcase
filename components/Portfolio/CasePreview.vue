<template>
	<div class="case">
		<nuxt-link :to="'/portfolio/case-' + id">
			<img :src="thumbnail" alt="">
		</nuxt-link>
	</div>
</template>

<script>

	export default {
		props: {
			id: {
				type: String,
				required: true
			},
			title: {
				type: String,
				required: true
			},
			thumbnail: {
				type: String,
				required: true
			}
		},
	}
</script>

<style lang="scss" scoped>

	$case-height-desktop: 400px;

	.case {
		margin-bottom: $gutter-mobile;
		height: $case-height-desktop;
		overflow: hidden;

		@include media(md) {
			lost-column: 1/2 2 $content-padding;
		}

		@include media(lg) {
			lost-column: 1/3 3 $content-padding;
		}

		a {
			display: flex;
			align-items: center;

			img {
				height: $case-height-desktop;
				object-fit: cover;
				@include transition;

				@include hover-state {
				};
			}
		}
	}

</style>
