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
	import TheHero from '~/components/Layout/TheHero';
	import TheFooter from '~/components/Layout/TheFooter';

	export default {
		components: {
			TheHeader,
			TheHero,
			TheFooter
		}
	}
</script>
