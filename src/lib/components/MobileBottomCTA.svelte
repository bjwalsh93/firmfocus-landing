<script lang="ts">
	let visible = $state(false);

	function handleScroll() {
		visible = window.scrollY > 600;
	}
</script>

<svelte:window onscroll={handleScroll} />

{#if visible}
	<div class="fixed bottom-0 left-0 right-0 z-40 lg:hidden glass border-t border-white/10 p-3 pb-[calc(0.75rem+env(safe-area-inset-bottom))]">
		<a
			href="https://simplexbi.com/products/"
			class="flex items-center justify-center gap-2 w-full py-3 bg-electric hover:bg-electric-light text-white font-semibold rounded-xl transition-all shadow-lg shadow-electric/20"
		>
			Get Started — From $299/mo
			<svg class="w-4 h-4" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2"><path d="M13 7l5 5m0 0l-5 5m5-5H6"/></svg>
		</a>
	</div>
{/if}
