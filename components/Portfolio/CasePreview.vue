<template>
	<div class="case-preview" :class="classes">
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
			thumbnail: {
				type: String,
				required: true
			},
			classes: {
				type: String,
				required: true,
				default: 'one-fourth'
			}
		},
	}
</script>

<style lang="scss">

	$case-height-md: 300px;
	$case-height-xl: 400px;

	.case-preview {
		margin-bottom: $gutter-small;
		background-color: $color-white;

		@include hover-state {
			a {
				img {
					transform: scale(1.04);
				}
			}
		};

		&.one-third {
			@include media(md) {
				lost-column: 1/3 3 $content-padding;
			}
		}

		&.one-fourth {
			@include media(md) {
				lost-column: 1/4 4 $content-padding;
			}
		}

		a {
			display: flex;
			align-items: center;
			overflow: hidden;
			height: $case-height-md;

			@include media(xl) {
				height: $case-height-xl;
			}

			img {
				height: $case-height-md;
				object-fit: cover;
				@include transition;

				@include media(xl) {
					height: $case-height-xl;
				}
			}
		}

		&-content {
			padding: $content-padding;
		}
	}

</style>
