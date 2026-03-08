<script lang="ts">
	let mobileOpen = $state(false);
	let scrolled = $state(false);

	function handleScroll() {
		scrolled = window.scrollY > 20;
	}

	function closeMobile() {
		mobileOpen = false;
	}

	const links = [
		{ href: '/', label: 'FirmFocus' },
		{ href: '/reports', label: 'Reports' },
		{ href: '/pricing', label: 'Pricing' },
		{ href: '/services', label: 'Services' },
		{ href: '/about', label: 'About' },
		{ href: '/contact', label: 'Contact' }
	];
</script>

<svelte:window onscroll={handleScroll} />

<header
	class="fixed top-0 left-0 right-0 z-50 transition-all duration-300 {scrolled
		? 'glass border-b border-white/5 shadow-lg shadow-black/20'
		: 'bg-transparent'}"
>
	<nav class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
		<div class="flex items-center justify-between h-16 lg:h-18">
			<!-- Logo -->
			<a href="/" class="flex items-center gap-2 group">
				<div
					class="w-8 h-8 rounded-lg bg-electric/10 border border-electric/20 flex items-center justify-center group-hover:bg-electric/20 transition-colors"
				>
					<span class="text-electric font-bold text-sm">F</span>
				</div>
				<div class="flex flex-col">
					<span class="text-white font-semibold text-sm leading-tight">FirmFocus</span>
					<span class="text-white/40 text-[10px] leading-tight">by Simplex BI</span>
				</div>
			</a>

			<!-- Desktop links -->
			<div class="hidden lg:flex items-center gap-1">
				{#each links.slice(1) as link}
					<a
						href={link.href}
						class="px-3 py-2 text-sm text-white/60 hover:text-white rounded-lg hover:bg-white/5 transition-all"
					>
						{link.label}
					</a>
				{/each}
			</div>

			<!-- Desktop CTA -->
			<div class="hidden lg:flex items-center gap-3">
				<a
					href="/pricing"
					class="text-sm text-white/60 hover:text-white transition-colors"
				>
					View Plans
				</a>
				<a
					href="/reports"
					class="px-4 py-2 bg-electric hover:bg-electric-light text-white text-sm font-medium rounded-lg transition-all hover:shadow-lg hover:shadow-electric/20"
				>
					Get Started
				</a>
			</div>

			<!-- Mobile hamburger -->
			<button
				onclick={() => (mobileOpen = !mobileOpen)}
				class="lg:hidden p-2 text-white/60 hover:text-white"
				aria-label="Toggle menu"
			>
				{#if mobileOpen}
					<svg class="w-6 h-6" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
						<path d="M6 18L18 6M6 6l12 12" />
					</svg>
				{:else}
					<svg class="w-6 h-6" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
						<path d="M4 6h16M4 12h16M4 18h16" />
					</svg>
				{/if}
			</button>
		</div>
	</nav>

	<!-- Mobile menu -->
	{#if mobileOpen}
		<div class="lg:hidden glass border-t border-white/5">
			<div class="px-4 py-4 space-y-1">
				{#each links as link}
					<a
						href={link.href}
						onclick={closeMobile}
						class="block px-4 py-3 text-white/70 hover:text-white hover:bg-white/5 rounded-lg transition-all text-base"
					>
						{link.label}
					</a>
				{/each}
				<div class="pt-3 border-t border-white/5">
					<a
						href="/reports"
						class="block w-full text-center px-4 py-3 bg-electric hover:bg-electric-light text-white font-medium rounded-lg transition-all"
					>
						Get Started — $299/mo
					</a>
				</div>
			</div>
		</div>
	{/if}
</header>
