<template>
	<main class="layout-main">
		<TheHeader></TheHeader>
		<nuxt/>
		<TheFooter></TheFooter>
	</main>
</template>

<script>
	import TheHeader from '~/components/Layout/TheHeader';
	import TheFooter from '~/components/Layout/TheFooter';

	export default {
		components: {
			TheHeader,
			TheFooter
		}
	}
</script>
