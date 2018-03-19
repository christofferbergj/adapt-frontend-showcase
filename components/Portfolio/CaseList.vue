<template>
	<div class="case-list">
		<CasePreview
			v-for="item in cases"
			:key="item.id"
			:id="item.id"
			:title="item.title"
			:thumbnail="item.thumbnail"
			:classes="classes">
		</CasePreview>
	</div>
</template>

<script>
	import CasePreview from '~/components/Portfolio/CasePreview';

	export default {
		props: {
			cases: {
				type: Array,
				required: true
			},
			classes: {
				type: String,
				required: true
			}
		},
		components: {
			CasePreview
		}
	}
</script>


<style lang="scss">

	.case-list {
		display: flex;
		flex-flow: row wrap;
		width: 100%;
	}

</style>
