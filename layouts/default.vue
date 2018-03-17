<template>
	<main class="l-main">
		<TheHeader></TheHeader>
		<TheHero></TheHero>
		<nuxt/>
		<TheFooter></TheFooter>
	</main>
</template>

<script>
	import TheHeader from '~/components/Layout/TheHeader';
	import TheFooter from '~/components/Layout/TheFooter';
	import TheHero from '~/components/Layout/TheHero';

	export default {
		components: {
			TheHeader,
			TheFooter,
			TheHero
		}
	}
</script>
