<script lang="ts">
	import Header from '$lib/components/Header.svelte';
	import '../lib/css/normallize.css';

	import { invalidate } from '$app/navigation'
	import { onMount } from 'svelte'

	export let data

	let { supabase, session } = data
	$: ({ supabase, session } = data)

	onMount(() => {
		const { data } = supabase.auth.onAuthStateChange((event, _session) => {
			if (_session?.expires_at !== session?.expires_at) {
				invalidate('supabase:auth')
			}
		})

		return () => data.subscription.unsubscribe()
	})
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
	<title>User Management</title>
</svelte:head>

<style lang="stylus">
	
	body
		margin 0
		padding 0

	main
		display flex
		justify-content center
		flex-direction column
		margin auto
		max-width: 1300px
		margin-top 16px

</style>
