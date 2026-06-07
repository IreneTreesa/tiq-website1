<script>
	let selectedYear = $state(2025);
	let preview = $state(null);

	const gallery = {
		2021: [
			"/media/2021/1.webp",
			"/media/2021/2.webp",
			"/media/2021/3.webp"
		],

		2022: [
			"/media/2022/1.webp",
			"/media/2022/2.webp",
			"/media/2022/3.webp"
		],

		2023: [
			"/media/2023/1.webp",
			"/media/2023/2.webp",
			"/media/2023/3.webp"
		],

		2024: [
			"/media/2024/1.webp",
			"/media/2024/2.webp",
			"/media/2024/3.webp"
		],
		2025: [
			"/media/2025/1.jpg",
			"/media/2025/4.jpg",
			"/media/2025/7.jpg"
		]

	};

	function setYear(year) {
		selectedYear = year;
	}

	function openPreview(img) {
		preview = img;
		document.body.style.overflow = 'hidden';
	}

	function closePreview() {
		preview = null;
		document.body.style.overflow = 'auto';
	}
</script>

<style>
	.no-scrollbar::-webkit-scrollbar {
		display: none;
	}

	.no-scrollbar {
		-ms-overflow-style: none;
		scrollbar-width: none;
	}
</style>

<div class="min-h-screen bg-gradient-to-tr from-[#020912] via-[#0b1320] to-[#101a2a] text-white">

	<!-- HERO -->
	<section class="px-6 md:px-12 pt-32 pb-16 text-center">

		

		<h1
			class="text-5xl md:text-7xl font-[merriweather]
			text-[#F5F1E8] mb-6"
		>
			Gallery
		</h1>

		<p
			class="max-w-2xl mx-auto text-white/60
			text-sm md:text-base leading-relaxed"
		>
			Moments, memories, victories, and chaos from TIQ across the years.
		</p>
	</section>

	<!-- YEAR TABS -->
	<section class="flex justify-center flex-wrap gap-4 px-6 mb-16">

		{#each [2021, 2022, 2023, 2024, 2025] as yr}

			<button
				on:click={() => setYear(yr)}
				class={`px-6 py-2 rounded-full border
				transition-all duration-300 text-sm tracking-wider

				${
					selectedYear === yr
					? 'bg-[#D4AF37] text-black border-[#D4AF37]'
					: 'border-white/10 text-white/70 hover:border-[#4FD1FF] hover:text-[#4FD1FF]'
				}`}
			>
				{yr}
			</button>

		{/each}

	</section>

	<!-- GALLERY GRID -->
	<section
		class="columns-1 sm:columns-2 lg:columns-3
		gap-4 space-y-4 px-4 md:px-10 pb-24"
	>

		{#each gallery[selectedYear] as img}

			<div
				class="break-inside-avoid overflow-hidden rounded-2xl
				border border-white/5 bg-[#0D1117]
				group cursor-pointer"
				on:click={() => openPreview(img)}
			>

				<img
					src={img}
					alt="gallery"
					loading="lazy"
					decoding="async"
					class="w-full object-cover
					transition duration-500
					group-hover:scale-105
					group-hover:opacity-90"
				/>

			</div>

		{/each}

	</section>

	<!-- LIGHTBOX -->
	{#if preview}

		<div
			class="fixed inset-0 z-[100]
			bg-black/95 backdrop-blur-sm
			flex items-center justify-center p-4"
		>

			<button
				on:click={closePreview}
				class="absolute top-6 right-6
				text-white/70 hover:text-white
				text-4xl transition"
			>
				✕
			</button>

			<img
				src={preview}
				alt="preview"
				class="max-w-[95vw] max-h-[90vh]
				object-contain rounded-xl"
			/>

		</div>

	{/if}

</div>