<template>
	<div class="l-content">
		<CaseList :cases="loadedCases"></CaseList>
	</div>
</template>

<script>
	import CaseList from '~/components/Portfolio/CaseList';

    export default {
		components: {
			CaseList
		},
	    data() {
		    return {
			    loadedCases: [
				    {
					    id: '1',
					    title: 'First Case',
					    thumbnail: 'https://images.freecreatives.com/wp-content/uploads/2016/07/Fancy-Mobile-App-p-UI-Mockup.png'
				    },
				    {
					    id: '2',
					    title: 'Second Case',
					    thumbnail: 'https://designshack.net/wp-content/uploads/Free-Perspective-Website-PSD-Mockup.jpg'
				    },
				    {
					    id: '3',
					    title: 'Third Case',
					    thumbnail: 'https://s3.envato.com/files/107529224/06.jpg'
				    },
				    {
					    id: '4',
					    title: 'Fourth Case',
					    thumbnail: 'https://cmkt-image-prd.global.ssl.fastly.net/0.1.0/ps/623544/580/473/m1/fpnw/wm0/03-.jpg?1481229950&s=959e2fd7cd3f55ba62a0f965d182db1d'
				    },
				    {
					    id: '5',
					    title: 'Fifth Case',
					    thumbnail: 'http://zidimperio.com/wp-content/uploads/mockup-for-web-design-40-free-website-mockup-psd-templates-xdesigns.png'
				    },
				    {
					    id: '6',
					    title: 'Sixth Case',
					    thumbnail: 'https://mockup.love/wp-content/uploads/edd/2017/12/Responsive-Website-Showcase-Mockup.jpg'
				    },
			    ]
		    }
	    }
    }
</script>

<style lang="scss" scoped>

</style>
