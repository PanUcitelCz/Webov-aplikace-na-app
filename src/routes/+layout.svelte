<script>
	import Header from '$lib/components/Header.svelte';
	import '../lib/css/normallize.css';
</script>

<Header />
<main>
	<slot />
</main>
<svelte:head>
	<link rel="preconnect" href="https://fonts.googleapis.com" />
	<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin="" />
	<link
		href="https://fonts.googleapis.com/css2?family=Bricolage+Grotesque:opsz,wght@10..48,200;10..48,600&display=swap"
		rel="stylesheet"
	/>
</svelte:head>

<style lang="stylus">
	
	body
		margin 0
		padding 0

	main
		margin 0 auto
		max-width 1300px
		padding 12px
		display grid

		display: grid;
		grid-template-columns: repeat(1, 1fr);
		grid-template-rows: repeat(2, 1fr);
		grid-column-gap: 21px;
		grid-row-gap: 21px; 

		@media only screen and (min-width 641px)
			padding 24px
			grid-template-columns: repeat(2, 1fr);

		@media only screen and (min-width 1024px)
			padding 24px
			grid-template-columns: repeat(3, 1fr);
</style>
