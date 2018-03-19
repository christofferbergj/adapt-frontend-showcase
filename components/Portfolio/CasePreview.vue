<template>
	<div class="cases">
		<div class="case-preview" v-for="item in cases" :class="classes" :key="item.id">
			<nuxt-link :to="'/portfolio/case-' + item.id">
				<img :src="item.thumbnail" alt="">
			</nuxt-link>
		</div>
	</div>
</template>

<script>

	export default {
		props: {
			cases: {
				type: Array,
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

	$case-height-sm: 200px;
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
			@include media(sm) {
				lost-column: 1/2 2 $content-padding;
			}
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
			height: $case-height-sm;

			@include media(md) {
				height: $case-height-md;
			}

			@include media(xl) {
				height: $case-height-xl;
			}

			img {
				height: $case-height-md;
				object-fit: cover;
				@include transition;
				width: 100%;

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
