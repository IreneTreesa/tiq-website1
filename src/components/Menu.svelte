<script>
	import { page } from '$app/stores';

	let tabs = [
		{ name: 'Home', link: '/' },
		{ name: 'About', link: '/about' },
		{ name: 'Gallery', link: '/gallery' },
		{ name: 'Archive', link: '/archive' },
		{ name: 'Team', link: '/team' }
	];

	let showMenu = false;

	function toggleMenu() {
		showMenu = !showMenu;

		// prevent background scroll
		document.body.style.overflow = showMenu ? 'hidden' : 'auto';
	}
</script>

<header
	class="top-0 w-full z-50
	bg-[#0b1320]"
>
	<div
	class="max-w-7xl mx-auto flex items-center justify-between
	px-5 md:px-8 py-3
	border-b border-white/10"
>
		<!-- LOGO -->
		<a href="/" class="z-50">
			<img
				src="/favicon.svg"
				alt="TIQ"
				class="w-14 md:w-16 h-auto"
			/>
		</a>

		<!-- DESKTOP NAV -->
		<nav class="hidden md:flex items-center gap-10">
			{#each tabs as tab}
				<a
					href={tab.link}
					class={`relative text-sm uppercase tracking-[0.2em]
					transition-all duration-300

					${
						$page.url.pathname === tab.link
							? 'text-[#D4AF37]'
							: 'text-white/80 hover:text-[#4FD1FF]'
					}`}
				>
					{tab.name}

					{#if $page.url.pathname === tab.link}
						<span
							class="absolute left-0 -bottom-2 w-full h-[1px]
							bg-[#D4AF37]"
						/>
					{/if}
				</a>
			{/each}
		</nav>

		<!-- MOBILE BUTTON -->
		<button
			class="md:hidden z-50 text-white text-3xl"
			on:click={toggleMenu}
			aria-label="Toggle Menu"
		>
			{showMenu ? '✕' : '☰'}
		</button>
	</div>

	<!-- FULLSCREEN MOBILE MENU -->
	{#if showMenu}
		<div
			class="fixed inset-0 z-[100] bg-[#05070B]
			flex flex-col justify-center items-center
			md:hidden"
		>

		<!-- CLOSE BUTTON (NEW) -->
		<button
			class="absolute top-6 right-6 text-white text-4xl"
			on:click={toggleMenu}
			aria-label="Close Menu"
		>
			✕
		</button>

			<nav class="flex flex-col items-center gap-8">
				{#each tabs as tab}
					<a
						href={tab.link}
						on:click={toggleMenu}
						class={`text-3xl uppercase tracking-[0.15em]
						transition-all duration-300

						${
							$page.url.pathname === tab.link
								? 'text-[#D4AF37]'
								: 'text-white hover:text-[#4FD1FF]'
						}`}
					>
						{tab.name}
					</a>
				{/each}
			</nav>

			
		</div>
	{/if}
</header>
