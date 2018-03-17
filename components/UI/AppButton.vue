<template>
	<button class="btn" :class="btnClass">
		<slot>
			<span>see more</span>
		</slot>
	</button>
</template>

<script>
	export default {
		props: {
			btnClass: {
				type: String,
				default: 'btn--primary',
				required: false
			},
		}
	}
</script>


<style lang="scss" scoped>

	.btn {
		@include transition();
		@include font-size(16px);
		border-radius: 25px;
		color: $color-font;
		text-transform: uppercase;
		display: inline-block;
		padding: 15px 30px;
		margin-top: 6px;
		margin-bottom: 6px;
		border: none;
		cursor: pointer;
		touch-action: manipulation;
		background-image: none;
		text-align: center;
		vertical-align: middle;
		white-space: nowrap;
		position: relative;
		overflow: hidden;
		font-weight: bold;

		@include hover-state {
			outline: 0;
			text-decoration: none;
		};

		&--primary {
			background: $color-primary-gradient;
			color: $color-white;
			position: relative;

			&:after {
				@include transition;
				position: absolute;
				content: '';
				top: 0;
				left: 0;
				width: 100%;
				height: 100%;
				background: $color-primary-gradient-reversed;
				z-index: 2;
				opacity: 0;
			}

			@include hover-state {

				&:after {
					opacity: 1;
				}
			};

			span {
				position: relative;
				z-index: 3;
			}
		}
	}
</style>
