<script>
	import { teams } from '../../data/team';
	import { Linkedin } from 'lucide-svelte';
	
</script>

<div class="min-h-screen bg-gradient-to-tr from-[#020912] via-[#0b1320] to-[#101a2a] text-white">

	<!-- HERO -->
	<section class="px-6 md:px-12 pt-32 pb-20 text-center">

		<p class="uppercase tracking-[0.4em] text-sm text-[#4FD1FF]/70 mb-4">
			THE PEOPLE BEHIND TIQ
		</p>

		<h1
			class="text-5xl md:text-7xl
			font-[merriweather] text-[#F5F1E8] mb-6"
		>
			Team
		</h1>

		<p class="max-w-2xl mx-auto text-white/60 leading-relaxed">
			The organisers, coordinators, designers, quizmasters,
			and chaos managers behind TIQ.
		</p>

	</section>

	

	<!-- CORE TEAM -->
	<section class="px-6 md:px-12 py-24">

	<h2 class="text-4xl font-[merriweather] mb-14">
		Core Team
	</h2>

	<div
		class="grid grid-cols-1
		md:grid-cols-2
		xl:grid-cols-4
		gap-6"
	>

		{#each teams[2025].core as member}

			<div
				class="relative rounded-2xl
				overflow-hidden
				border border-white/10
				bg-[#0D1117]"
			>

				<!-- LINKEDIN BUTTON -->
				<a
	href={member.linkedin}
	target="_blank"
	class="absolute top-4 right-4
	z-10 p-2 rounded-full
	bg-black/40 backdrop-blur-sm
	text-white/60
	hover:text-[#4FD1FF]
	hover:bg-black/60
	transition"
>

	<Linkedin size={16} strokeWidth={1.8} />

</a>

				<!-- IMAGE -->
				<img
					src={member.image}
					alt={member.name}
					class="w-full h-[240px]
					object-cover"
				/>

				<!-- CONTENT -->
				<div class="p-5">

					<h3
						class="text-xl font-[merriweather]
						mb-2"
					>
						{member.name}
					</h3>

					<p class="text-white/50 text-sm">
						{member.role}
					</p>

				</div>

			</div>

		{/each}

	</div>

</section>

	<!-- TEAM MEMBERS -->
	<section class="px-6 md:px-12 pb-32">

	<h2 class="text-4xl font-[merriweather] mb-10">
		Team Members
	</h2>

	<div
		class="columns-1 md:columns-2 xl:columns-3
		gap-12"
	>

		{#each teams[2025].members as member}

			<div class="mb-4 break-inside-avoid">

				<p class="text-white/70 leading-relaxed">
					• {member}
				</p>

			</div>

		{/each}

	</div>

</section>

</div>