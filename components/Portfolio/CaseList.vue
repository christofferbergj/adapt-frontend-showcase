<template>
	<div class="case-list">
		<CasePreview
			v-for="item in cases"
			:key="item.id"
			:id="item.id"
			:title="item.title"
			:thumbnail="item.thumbnail">
		</CasePreview>
	</div>
</template>

<script>
	import CasePreview from '~/components/Portfolio/CasePreview';

	export default {
		components: {
			CasePreview
		},

		props: {
			cases: {
				type: Array,
				required: true
			}
		}
	}
</script>


<style lang="scss" scoped>

	.case-list {
		display: flex;
		flex-flow: row wrap;
		width: 100%;
		background-color: $color-white;
		padding: $content-padding;
		border-radius: $border-radius-default;
	}

</style>
