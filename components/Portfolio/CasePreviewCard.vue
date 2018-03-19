<template>
	<div class="cases">
		<div class="case-card"
		     v-for="item in cases"
		     :key="item.id"
		     :class="classes">

			<nuxt-link :to="'/portfolio/case-' + item.id">
				<img :src="item.thumbnail" alt="">
			</nuxt-link>

			<div class="content">
				<h2>{{ item.title }}</h2>
				<p>{{ item.description }}</p>
			</div>
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

	$case-height-md: 300px;
	$case-height-xl: 400px;

	.cases {
		display: flex;
		flex-flow: row wrap;

		.case-card {
			margin-bottom: $gutter-small;
			background-color: $color-white;

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

					@include hover-state {
						transform: scale(1.04);
					};
				}
			}

			.content {
				padding: $content-padding;
			}
		}
	}

</style>
