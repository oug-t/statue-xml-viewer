<script>
	import { Hero, Stats, Categories, LatestContent, BuiltBy } from 'statue-ssg';

	const { data } = $props();
</script>

<svelte:head>
	<title>Statue</title>
	<meta
		name="description"
		content="Statue SSG powered by Svelte, generates static sites from markdown content."
	/>
</svelte:head>

<div
	class="min-h-screen bg-linear-to-b from-(--color-hero-from) via-(--color-hero-via) to-(--color-hero-to)"
>
	<div class="w-full max-w-3xl mx-auto px-4 py-16 text-center flex flex-col items-center">
		
		<div class="inline-block px-4 py-1.5 mb-6 rounded-full bg-blue-500/10 border border-blue-400/20 backdrop-blur-sm">
			<span class="text-sm font-mono font-semibold text-blue-200 tracking-tight">
				⚡ Implemented in 1 hour
			</span>
		</div>

		<h2 class="text-5xl font-black text-white tracking-tight drop-shadow-xl mb-4">
			XML Viewer Demo
		</h2>
		
		<p class="text-xl text-gray-300 max-w-xl mx-auto leading-relaxed mb-10">
			Native DOM rendering.
			<br />
			<span class="opacity-75 text-base">Interact with raw XML, SVG, and RSS feeds.</span>
		</p>

		<div class="flex flex-col items-center gap-4">
			<a href="/demo" class="demo-btn group">
				<span class="text-xl group-hover:scale-110 transition-transform duration-200">▶</span>
				<span>Try the Live Demo</span>
			</a>
		</div>

	</div>
</div>

<style>
	:global(html) {
		scroll-behavior: smooth;
	}

	.stats-wrapper :global(.container) {
		padding-top: 1rem !important;
	}

	.typewriter-showcase {
		max-width: 1200px;
		margin: 0 auto;
		padding: 1rem 2rem 0;
		text-align: center;
		position: relative;
		z-index: 10;
	}

	.demo-btn {
		display: inline-flex;
		align-items: center;
		gap: 0.75rem;
		padding: 0.75rem 2.5rem;
		background-color: white;
		color: var(--color-hero-from);
		text-decoration: none;
		border-radius: 9999px; /* Pill shape */
		font-weight: 800;
		font-size: 1.1rem;
		box-shadow: 0 4px 20px rgba(0, 0, 0, 0.2);
		transition: all 0.2s cubic-bezier(0.4, 0, 0.2, 1);
	}

	.demo-btn:hover {
		transform: translateY(-2px) scale(1.02);
		box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
		background-color: #f8fafc;
	}
</style>
