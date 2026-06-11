<script>
	import { page } from '$app/stores';
	import { archives } from '../../../data/archive';
import { Eye, Download } from "lucide-svelte";
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

{#if data.winners}
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

						

					</div>

				{/each}

			</div>

		</div>

	</div>

</section>

{/if}

	<!-- REPORTS -->
	{#if data.reports}

<section class="px-6 md:px-12 py-24">

	<h2 class="text-4xl font-[merriweather] mb-12">
		Reports
	</h2>

	<div class="grid grid-cols-1 md:grid-cols-2 gap-5 max-w-9xl">

		<!-- MAIN REPORT -->
		{#if data.reports.main}

			<div
	class="rounded-2xl border border-white/10
	bg-[#0D1117]
	p-6 hover:border-[#4FD1FF]/40 transition"
>

				<div class="flex items-center justify-between gap-6">

					<div>

						<h3 class="text-xl lg:text-2xl font-[merriweather] mb-2">
							TIQ {data.year} Report
						</h3>

						

					</div>

					<div class="flex items-center gap-4">

	<a
		href={data.reports.main}
		target="_blank"
		aria-label="View Report"
		class="text-[#4FD1FF] hover:scale-110 transition"
	>
		<Eye class="w-5 h-5" />
	</a>

	<a
		href={data.reports.main}
		download
		aria-label="Download Report"
		class="text-[#D4AF37] hover:scale-110 transition"
	>
		<Download class="w-5 h-5" />
	</a>

</div>

				</div>

			</div>

		{/if}

		<!-- ANNUAL REPORT -->
		{#if data.reports.annual}

			<div
	class="rounded-2xl border border-white/10
	bg-[#0D1117]
	p-6 hover:border-[#4FD1FF]/40 transition"
>

				<div class="flex items-center justify-between gap-6">

					<div>

						<h3 class="text-2xl font-[merriweather] mb-2">
							Annual Club Report
						</h3>

						
					</div>

					<div class="flex items-center gap-4">

	<a
		href={data.reports.main}
		target="_blank"
		aria-label="View Report"
		class="text-[#4FD1FF] hover:scale-110 transition"
	>
		<Eye class="w-5 h-5" />
	</a>

	<a
		href={data.reports.main}
		download
		aria-label="Download Report"
		class="text-[#D4AF37] hover:scale-110 transition"
	>
		<Download class="w-5 h-5" />
	</a>

</div>

				</div>

			</div>

		{/if}

	</div>

</section>

{/if}

	<!-- OTHER EVENTS -->
{#if data.events && data.events.length > 0}
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
{/if}

	<!-- GALLERY PREVIEW -->
	<section class="px-6 md:px-12 pb-32">

	<div
		class="max-w-4xl mx-auto
		text-center
		border border-white/10
		bg-[#0D1117]
		rounded-3xl
		p-10"
	>

		<h2
			class="text-4xl font-[merriweather]
			text-white"
		>
			Gallery
		</h2>

		<p
			class="mt-4 text-white/70
			max-w-2xl mx-auto"
		>
			Explore photographs and memories from
			TIQ {data.year}.
		</p>

		<a
			href="/gallery"
			class="inline-flex items-center justify-center
			mt-8 px-6 py-3
			border border-[#4FD1FF]
			text-[#4FD1FF]
			rounded-full
			hover:bg-[#4FD1FF]
			hover:text-[#020912]
			transition"
		>
			View Gallery
		</a>

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