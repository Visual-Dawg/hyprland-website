<script>
	import Title from '$lib/components/Title.svelte'
	import CardsContainer from '$lib/components/CardsContainer.svelte'
	import PluginCard from './PluginCard.svelte'

	export let data

	const { plugins } = data
</script>

<svelte:head>
	<title>{'Plugins'}</title>
</svelte:head>

<section>
	<header class="header mt-24 md:mt-32 lg:mt-48">
		<Title class="mb-0  duration-1000 animate-in fade-in-0">
			<span slot="pre">Plugins</span>
			<span slot="title">Unlock full power</span><span slot="subtitle">
				Easily load up plugins and customize everything
			</span>
		</Title>
	</header>

	<CardsContainer
		class="flex w-full max-w-screen-3xl grid-flow-dense grid-cols-2 flex-col gap-4 animate-in  fade-in-0 slide-in-from-bottom-6 fill-mode-backwards [animation-delay:800ms] [animation-duration:1500ms] lg:grid 2xl:grid-cols-6"
	>
		{#each plugins as plugin, index}
			<PluginCard
				{plugin}
				class={plugin.banner
					? plugin.featured
						? '2xl:col-span-4'
						: index % 2
							? '2xl:col-span-4'
							: '2xl:col-span-2'
					: '2xl:col-span-2'}
				color={index % 3 === 0 ? 'purple' : 'cyan'}
			/>
		{/each}
	</CardsContainer>
</section>

<style lang="postcss">
	section {
		@apply relative flex min-h-screen flex-col items-center justify-center gap-14 overflow-hidden px-6;
	}

	.header {
		/* display: flex;
		justify-content: center;
		align-items: center;
		position: relative;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		height: 100%; */
		/* margin-bottom: 8rem; */
	}
</style>