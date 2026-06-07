<script>
	import { page } from '$app/stores';
	import { archives } from '../../../data/archive';

	const year = Number($page.params.year);

	const data = archives.find((a) => a.year === year);
</script>

{#if data}

<div class="min-h-screen bg-gradient-to-tr from-[#020912] via-[#0b1320] to-[#101a2a] text-white">

	<!-- HERO -->
	<section
		class="relative min-h-[85vh]
		flex items-end px-6 md:px-12 py-24 overflow-hidden"
	>

		<img
			src={data.poster}
			alt={data.title}
			class="absolute inset-0 w-full h-full object-cover opacity-80"
		/>

		<div
			class="absolute inset-0
			bg-gradient-to-t from-[#05070B] via-black/20 to-transparent"
		/>

		<div class="relative z-10 max-w-3xl">

			<p class="text-[#D4AF37] tracking-[0.4em] text-sm mb-4">
	{data.edition}
</p>

<h1
	class="text-5xl md:text-7xl
	font-[merriweather] mb-8"
>
	{data.title}
</h1>

<div class="space-y-3 text-white/70 text-lg">

	<p>
		{data.date}
	</p>

	<p>
		{data.venue}
	</p>

	<p>
		Quizmaster — {data.quizmaster}
	</p>

</div>

		</div>

	</section>

	<!-- WINNERS -->
	<section class="px-6 md:px-12 py-24">

	<h2 class="text-4xl font-[merriweather] mb-14">
		Podium
	</h2>

	<div class="grid lg:grid-cols-3 gap-8">

		<!-- FIRST -->
		<div
			class="rounded-3xl border border-[#D4AF37]/30
			bg-[#0D1117] p-10"
		>

			<p class="text-[#D4AF37] uppercase tracking-[0.3em] text-sm mb-8">
				Winners
			</p>

			<div class="space-y-6">

				{#each data.winners.first as person}

					<div>

						<h3 class="text-2xl font-[merriweather]">
							{person.name}
						</h3>

						{#if person.college}
							<p class="text-white/40 mt-1">
								{person.college}
							</p>
						{/if}

					</div>

				{/each}

			</div>

		</div>

		<!-- SECOND -->
		<div
			class="rounded-3xl border border-white/10
			bg-[#0D1117] p-10"
		>

			<p class="text-white/50 uppercase tracking-[0.3em] text-sm mb-8">
				Runners Up
			</p>

			<div class="space-y-6">

				{#each data.winners.second as person}

					<div>

						<h3 class="text-2xl font-[merriweather]">
							{person.name}
						</h3>

						{#if person.college}
							<p class="text-white/40 mt-1">
								{person.college}
							</p>
						{/if}

					</div>

				{/each}

			</div>

		</div>

		<!-- THIRD -->
		<div
			class="rounded-3xl border border-white/10
			bg-[#0D1117] p-10"
		>

			<p class="text-white/50 uppercase tracking-[0.3em] text-sm mb-8">
				Second Runners Up
			</p>

			<div class="space-y-6">

				{#each data.winners.third as person}

					<div>

						<h3 class="text-2xl font-[merriweather]">
							{person.name}
						</h3>

						{#if person.college}
							<p class="text-white/40 mt-1">
								{person.college}
							</p>
						{/if}

					</div>

				{/each}

			</div>

		</div>

	</div>

</section>

	<!-- REPORTS -->
	{#if data.reports}

<section class="px-6 md:px-12 pb-24">

	<h2 class="text-4xl font-[merriweather] mb-12">
		Reports
	</h2>

	<div class="flex flex-col gap-5 max-w-4xl">

		<!-- MAIN REPORT -->
		{#if data.reports.main}

			<a
				href={data.reports.main}
				target="_blank"
				class="rounded-2xl border border-white/10
				bg-[#0D1117]
				p-6 hover:border-[#4FD1FF]/40 transition"
			>

				<div class="flex items-center justify-between gap-6">

					<div>

						<h3 class="text-2xl font-[merriweather] mb-2">
							TIQ {data.year} REPORT
						</h3>

						

					</div>

					<div
						class="flex gap-6 text-sm uppercase tracking-[0.2em]"
					>

						<span class="text-[#4FD1FF]">
							View
						</span>

						<span class="text-[#D4AF37]">
							Download
						</span>

					</div>

				</div>

			</a>

		{/if}

		<!-- ANNUAL REPORT -->
		{#if data.reports.annual}

			<a
				href={data.reports.annual}
				target="_blank"
				class="rounded-2xl border border-white/10
				bg-[#0D1117]
				p-6 hover:border-[#D4AF37]/40 transition"
			>

				<div class="flex items-center justify-between gap-6">

					<div>

						<h3 class="text-2xl font-[merriweather] mb-2">
							ANNUAL CLUB REPORT
						</h3>

						
					</div>

					<div
						class="flex gap-6 text-sm uppercase tracking-[0.2em]"
					>

						<span class="text-[#4FD1FF]">
							View
						</span>

						<span class="text-[#D4AF37]">
							Download
						</span>

					</div>

				</div>

			</a>

		{/if}

	</div>

</section>

{/if}

	<!-- OTHER EVENTS -->
	<section class="px-6 md:px-12 pb-24">

	<h2 class="text-4xl font-[merriweather] mb-12">
		Other Events
	</h2>

	<div class="grid lg:grid-cols-2 gap-10">

		{#each data.events as event}

			<div
				class="rounded-3xl overflow-hidden
				border border-white/10
				bg-[#0D1117]"
			>

				<!-- IMAGE -->
				<div class="relative">

					<img
						src={event.image}
						alt={event.title}
						class="w-full h-[320px] object-cover"
					/>

					<div
						class="absolute inset-0
						bg-gradient-to-t from-black via-black/20 to-transparent"
					/>

					<h3
						class="absolute bottom-6 left-6
						text-3xl font-[merriweather]"
					>
						{event.title}
					</h3>

				</div>

				<!-- CONTENT -->
				<div class="p-8 space-y-5">

					<div class="flex flex-col gap-2 text-white/50 text-sm">

						<p>
							{event.date}
						</p>

						<p>
							{event.venue}
						</p>

					</div>

					<p class="text-white/70 leading-relaxed">
						{event.description}
					</p>

					

				</div>

			</div>

		{/each}

	</div>

</section>

	<!-- GALLERY PREVIEW -->
	<section class="px-6 md:px-12 pb-32">

		<div class="flex items-center justify-between mb-12">

			<h2 class="text-4xl font-[merriweather]">
				Gallery
			</h2>

			<a
				href="/gallery"
				class="text-[#4FD1FF] hover:text-[#D4AF37] transition"
			>
				View Full Gallery →
			</a>

		</div>

		<div class="grid grid-cols-1 md:grid-cols-3 gap-6">

			{#each data.gallery as img}

				<img
					src={img}
					alt="gallery"
					class="rounded-3xl object-cover
					h-[320px] w-full"
				/>

			{/each}

		</div>

	</section>

</div>

{:else}

<div
	class="min-h-screen bg-[#05070B]
	text-white flex items-center justify-center"
>

	<h1 class="text-4xl font-[merriweather]">
		Archive Not Found
	</h1>

</div>

{/if}