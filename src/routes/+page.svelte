<script lang="ts">

	import Card from "$components/Card.svelte";
    // heslo k databasi cGCXJCIStjvqWo2A
    // nazev databaze Web_app

    import { Auth } from '@supabase/auth-ui-svelte'
	import { ThemeSupa } from '@supabase/auth-ui-shared'

	export let data

</script>

<!-- src/routes/+page.svelte -->

<svelte:head>
	<title>User Management</title>
</svelte:head>

<div class="log">
	<div class="col-6 form-widget">
		<Auth
			supabaseClient={data.supabase}
			view="magic_link"
			redirectTo={`${data.url}/auth/callback`}
			showLinks={false}
			appearance={{ theme: ThemeSupa, style: { input: 'color: black' } }}
		/>
	</div>
</div>
<div class="grid">
   <Card src="https://info.zcu.cz/image?obrazek=11912&type=masonry" href="/">Aplikace pro podporu výuky</Card>
</div>

<style lang="stylus">

    .grid
        width 100%
        margin 0 auto
        max-width 1300px
        padding 12px
        display grid
        justify-content center

        grid-template-columns repeat(1, 1fr)
        grid-template-rows repeat(2, 1fr)
        grid-column-gap 21px
        grid-row-gap 21px

        @media only screen and (min-width 641px)
            padding 24px
            grid-template-columns: repeat(2, 1fr)

        @media only screen and (min-width 1024px)
            padding 24px
            grid-template-columns: repeat(3, 1fr)

    .log
        width 100%
        display flex
        justify-content center
        color black

        input
            color black

        textarea
            color #000

</style>