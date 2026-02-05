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
	<Hero />

    <div class="flex justify-center py-8">
        <a href="/demo" class="demo-btn">
            View XML Component Demo
        </a>
    </div>

	<section class="typewriter-showcase">
		<BuiltBy />
	</section>

	<div class="stats-wrapper">
		<Stats />
	</div>

	<div class="container mx-auto px-4 py-10">
		<Categories directories={data.directories} />

		<LatestContent rootContent={data.rootContent} />
	</div>
</div>

<style>
	/* Add smooth scroll behavior */
	:global(html) {
		scroll-behavior: smooth;
	}

	/* Reduce padding of Stats component on this page to sit closer to BuiltBy */
	.stats-wrapper :global(.container) {
		padding-top: 1rem !important;
	}

	/* Typewriter Showcase Section */
	.typewriter-showcase {
		max-width: 1200px;
		margin: 0 auto;
		padding: 1rem 2rem 0;
		text-align: center;
		position: relative;
		z-index: 10;
	}

    .demo-btn {
        display: inline-block;
        padding: 0.75rem 1.5rem;
        background-color: var(--color-hero-from); /* Uses your existing theme vars */
        color: white;
        text-decoration: none;
        border-radius: 0.5rem;
        font-weight: 600;
        transition: transform 0.2s, filter 0.2s;
        box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1);
    }

    .demo-btn:hover {
        transform: translateY(-2px);
        filter: brightness(1.1);
    }
</style>
