<script>
	import XmlViewer from '$lib/components/XmlViewer.svelte';

	let xmlString = `<rss version="2.0"><channel><title>Statue XML</title><item><desc>Native rendering</desc></item></channel></rss>`;
</script>

<svelte:head><title>XML Viewer</title></svelte:head>

<div class="min-h-screen bg-linear-to-b from-(--color-hero-from) to-gray-900 pt-32 pb-12 px-4 flex flex-col items-center">
	<div class="w-full max-w-4xl space-y-6">
		
		<div class="flex items-center justify-between text-white">
			<h1 class="text-2xl font-bold">XML Viewer</h1>
			<a href="/" class="text-sm text-gray-400 hover:text-white transition">← Back Home</a>
		</div>

		<div class="bg-gray-900 rounded-xl shadow-2xl border border-gray-700 overflow-hidden">
			<div class="flex items-center justify-between p-4 bg-gray-800/40 border-b border-gray-700">
				<label class="bg-blue-600 hover:bg-blue-500 text-white px-4 py-1.5 rounded-md text-sm font-medium cursor-pointer transition">
					Upload File
					<input 
						type="file" 
						accept=".xml,.svg,.rss,.atom,.xhtml" 
						class="hidden" 
						on:change={e => e.target.files[0]?.text().then(t => xmlString = t)} 
					/>
				</label>
				<span class="text-xs font-mono text-gray-500">Supports .xml .svg .rss</span>
			</div>
			
			<div class="bg-[#282c34]">
				<XmlViewer {xmlString} />
			</div>
		</div>

	</div>
</div>

<style>
	:global(.xml-container) {
		margin: 0 !important;
		border-radius: 0 !important;
		box-shadow: none !important;
		min-height: 300px;
	}
</style>
