<script>
	import { Instagram, Linkedin, Twitter, Mail, MapPin } from "lucide-svelte";
</script>

<footer class="w-full bg-[#A9D1F7] text-[#0B1E3F]">

	<div class="max-w-6xl mx-auto px-6 py-10">

		<!-- TOP: BRAND -->
		<div class="text-center space-y-3">

			<h2 class="text-2xl md:text-3xl font-[merriweather] font-semibold">
				The Illuminati Quiz
			</h2>

			<p class="text-xs uppercase tracking-widest text-gray-700 mt-1">Since 2008</p>

			<p class="text-sm text-[#0B1E3F]/70 max-w-xl mx-auto leading-relaxed font-['Figtree']">
				South India’s largest intercollegiate quizzing experience,
				built at Govt. Model Engineering College.
			</p>

			<p class="flex items-center justify-center gap-2 text-sm text-[#0B1E3F]/60 font-['Figtree']">
				<MapPin class="w-4 h-4" />
				Thrikkakara, Kerala
			</p>

		</div>

		<!-- DIVIDER -->
		<div class="my-6 border-t border-[#0B1E3F]/10"></div>

		<!-- LINKS (MINIMAL INLINE STYLE) -->
		<div class="flex flex-wrap justify-center gap-x-6 gap-y-2 text-sm text-[#0B1E3F]/70 font-['Figtree']">

			<a href="/" class="hover:text-[#70B5F4] transition">Home</a>
			<span class="opacity-30">|</span>

			<a href="/about" class="hover:text-[#70B5F4] transition">About</a>
			<span class="opacity-30">|</span>

			<a href="/gallery" class="hover:text-[#70B5F4] transition">Gallery</a>
			<span class="opacity-30">|</span>

			<a href="/archive" class="hover:text-[#70B5F4] transition">Archive</a>
			<span class="opacity-30">|</span>

			<a href="/team" class="hover:text-[#70B5F4] transition">Team</a>

		</div>

		<!-- SOCIAL ROW -->
		<div class="mt-10 flex justify-center gap-4">

			<a href="https://www.instagram.com/mec_illuminati"
				target="_blank"
				class="p-2 rounded-full border border-[#0B1E3F]/10
				hover:border-[#70B5F4] hover:bg-[#70B5F4]/10 transition">
				<Instagram class="w-5 h-5" />
			</a>

			<a href="https://www.linkedin.com/company/illuminati-quiz-club/"
				target="_blank"
				class="p-2 rounded-full border border-[#0B1E3F]/10
				hover:border-[#70B5F4] hover:bg-[#70B5F4]/10 transition">
				<Linkedin class="w-5 h-5" />
			</a>

			<a href="https://x.com/IlluminatiQuiz"
				target="_blank"
				class="p-2 rounded-full border border-[#0B1E3F]/10
				hover:border-[#70B5F4] hover:bg-[#70B5F4]/10 transition">
				<svg 
  xmlns="http://www.w3.org/2000/svg" 
  viewBox="0 0 24 24" 
  fill="none" 
  stroke="currentColor" 
  stroke-width="2" 
  stroke-linecap="round" 
  stroke-linejoin="round" 
  class="w-5 h-5 text-[#0B1E3F] group-hover:text-[#70B5F4] transition flex-shrink-0"
>
  <path d="M4 4l11.733 16h4.267l-11.733 -16z" />
  <path d="M4 20l6.768 -6.768m2.46 -2.46l6.772 -6.772" />
</svg>
			</a>


			<a href="mailto:illuminatiquiz@gmail.com"
				class="p-2 rounded-full border border-[#0B1E3F]/10
				hover:border-[#70B5F4] hover:bg-[#70B5F4]/10 transition">
				<Mail class="w-5 h-5" />
			</a>

		</div>

		<!-- BOTTOM LINE -->
		<div class="mt-10 text-center text-xs text-[#0B1E3F]/50 font-['Figtree']">
			© {new Date().getFullYear()} The Illuminati Quiz Club
		</div>

	</div>

</footer>