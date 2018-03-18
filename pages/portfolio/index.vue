<template>
	<div class="portfolio">
		<case-preview-card :cases="loadedCases" :classes="'one-fourth'"></case-preview-card>
	</div>
</template>

<script>
	import CasePreviewCard from '~/components/Portfolio/CasePreviewCard';

	export default {
		components: {
			CasePreviewCard
		},
		data() {
			return {
				loadedCases: [
					{
						id: '1',
						title: '1 - Case Title',
						description: 'This is the description of the case - 1',
						thumbnail: 'https://images.freecreatives.com/wp-content/uploads/2016/07/Fancy-Mobile-App-p-UI-Mockup.png'
					},
					{
						id: '2',
						title: '2 - Case Title',
						description: 'This is the description of the case - 2',
						thumbnail: 'https://designshack.net/wp-content/uploads/Free-Perspective-Website-PSD-Mockup.jpg'
					},
					{
						id: '3',
						title: '3 - Case Title',
						description: 'This is the description of the case - 3',
						thumbnail: 'https://s3.envato.com/files/107529224/06.jpg'
					},
					{
						id: '4',
						title: '4 - Case Title',
						description: 'This is the description of the case - 4',
						thumbnail: 'https://cmkt-image-prd.global.ssl.fastly.net/0.1.0/ps/623544/580/473/m1/fpnw/wm0/03-.jpg?1481229950&s=959e2fd7cd3f55ba62a0f965d182db1d'
					},
					{
						id: '5',
						title: '5 - Case Title',
						description: 'This is the description of the case - 5',
						thumbnail: 'http://zidimperio.com/wp-content/uploads/mockup-for-web-design-40-free-website-mockup-psd-templates-xdesigns.png'
					},
					{
						id: '6',
						title: '6 - Case Title',
						description: 'This is the description of the case - 6',
						thumbnail: 'https://mockup.love/wp-content/uploads/edd/2017/12/Responsive-Website-Showcase-Mockup.jpg'
					},
					{
						id: '7',
						title: '7 - Case Title',
						description: 'This is the description of the case - 7',
						thumbnail: 'https://images.freecreatives.com/wp-content/uploads/2016/07/Fancy-Mobile-App-p-UI-Mockup.png'
					},
					{
						id: '8',
						title: '8 - Case Title',
						description: 'This is the description of the case - 8',
						thumbnail: 'https://designshack.net/wp-content/uploads/Free-Perspective-Website-PSD-Mockup.jpg'
					},
					{
						id: '9',
						title: '9 - Case Title',
						description: 'This is the description of the case - 9',
						thumbnail: 'https://s3.envato.com/files/107529224/06.jpg'
					},
					{
						id: '10',
						title: '10 - Case Title',
						description: 'This is the description of the case - 10',
						thumbnail: 'https://cmkt-image-prd.global.ssl.fastly.net/0.1.0/ps/623544/580/473/m1/fpnw/wm0/03-.jpg?1481229950&s=959e2fd7cd3f55ba62a0f965d182db1d'
					},
					{
						id: '11',
						title: '11 - Case Title',
						description: 'This is the description of the case - 11',
						thumbnail: 'http://zidimperio.com/wp-content/uploads/mockup-for-web-design-40-free-website-mockup-psd-templates-xdesigns.png'
					},
					{
						id: '12',
						title: '12 - Case Title',
						description: 'This is the description of the case - 12',
						thumbnail: 'https://mockup.love/wp-content/uploads/edd/2017/12/Responsive-Website-Showcase-Mockup.jpg'
					},
				]
			}
		}
	}
</script>

<style lang="scss" scoped>

	.portfolio {
		margin: 0 $gutter-small;
	}
</style>
