<script>
	import { archives } from '../../data/archive';
	import { onMount } from 'svelte';
	let loading = true;

onMount(() => {
	setTimeout(() => {
		loading = false;
	}, 600);
});
</script>


<div class="min-h-screen bg-gradient-to-tr from-[#020912] via-[#0b1320] to-[#101a2a] text-white px-6 md:px-12 py-15">

	<!-- HERO -->
	<section class="text-center mb-24">

		<p class="uppercase tracking-[0.4em] text-sm text-[#4FD1FF]/70 mb-4">
			TIQ ARCHIVES
		</p>

		<h1
			class="text-5xl md:text-7xl font-[merriweather]
			text-[#F5F1E8] mb-6"
		>
			Archive
		</h1>

		<p class="max-w-2xl mx-auto text-white/60 leading-relaxed">
			A preserved history of TIQ across the years.
		</p>

	</section>

	<!-- YEAR CARDS -->
	
{#if loading}

	<!-- SKELETON LOADING -->
	<section
		class="grid grid-cols-1 md:grid-cols-2 xl:grid-cols-3 gap-8 max-w-7xl mx-auto"
	>

		{#each Array(6) as _}

			<div
				class="h-[420px] rounded-3xl
				bg-[#162235] animate-pulse"
			/>

		{/each}

	</section>

{:else}

	<!-- REAL ARCHIVE GRID -->
	<section
		class="grid grid-cols-1 md:grid-cols-2 xl:grid-cols-3 gap-8 max-w-7xl mx-auto"
	>

		{#each archives as item}

			<a
				href={`/archive/${item.year}`}
				class="group relative overflow-hidden rounded-3xl
				border border-white/10 bg-[#0D1117]
				hover:border-[#D4AF37]/40 transition-all duration-500"
			>

				<img
					src={item.poster}
					alt={item.title}
					loading="lazy"
					decoding="async"
					class="h-[420px] w-full object-cover
					group-hover:scale-105 transition duration-700"
				/>

				<div
					class="absolute inset-0
					bg-gradient-to-t from-black via-black/40 to-transparent"
				/>

				<div class="absolute bottom-0 p-8">

					<p class="text-[#D4AF37] text-sm tracking-[0.3em] mb-3">
						{item.edition}
					</p>

					<h2 class="text-3xl font-[merriweather] mb-4 leading-tight">
						{item.title}
					</h2>

					<p class="text-white/60 text-sm">
						{item.date}
					</p>

				</div>

			</a>

		{/each}

	</section>

{/if}



</div>