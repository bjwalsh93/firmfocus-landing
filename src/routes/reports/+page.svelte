<script lang="ts">
	const categories = [
		{
			name: 'Working Timekeeper Reports',
			desc: 'Track billable hours, utilization rates, and timekeeper productivity. Understand who is billing, how much, and where the gaps are.',
			icon: '⏱',
			color: 'electric'
		},
		{
			name: 'Client / Matter Reports (By Professional)',
			desc: 'Financial performance broken down by professional — revenue, WIP, collections, and profitability at the client and matter level.',
			icon: '📋',
			color: 'accent-emerald'
		},
		{
			name: 'Inventory By Professional',
			desc: 'WIP and AR aging analysis, unbilled inventory tracking, and collection forecasting to keep your firm\'s cash flow healthy.',
			icon: '📊',
			color: 'accent-cyan'
		},
		{
			name: 'Matter Listings',
			desc: 'Comprehensive matter data views including status tracking, matter lifecycle reporting, and cross-matter analytics.',
			icon: '📁',
			color: 'purple-400'
		},
		{
			name: 'Trust',
			desc: 'Trust account balances, transaction histories, reconciliation reports, and compliance monitoring to keep your trust accounting airtight.',
			icon: '🔒',
			color: 'amber-400'
		},
		{
			name: 'Utilities',
			desc: 'System administration reports, data validation tools, and operational health checks to keep your Aderant environment running smoothly.',
			icon: '⚙️',
			color: 'rose-400'
		}
	];
</script>

<svelte:head>
	<title>Report Library — FirmFocus by Simplex BI</title>
	<meta name="description" content="Browse FirmFocus pre-built SSRS reports for Aderant Expert. Six categories covering timekeeping, client/matter analytics, inventory, trust, and more." />
</svelte:head>

<section class="pt-28 sm:pt-36 pb-20 sm:pb-28 relative">
	<div class="absolute inset-0 grid-bg"></div>
	<div class="absolute top-0 left-1/2 -translate-x-1/2 w-[600px] h-[400px] bg-electric/5 rounded-full blur-[120px]"></div>

	<div class="relative max-w-5xl mx-auto px-4 sm:px-6">
		<div class="text-center mb-14">
			<h1 class="text-4xl sm:text-5xl lg:text-6xl font-bold text-white leading-tight">
				Report Library
			</h1>
			<p class="text-lg text-white/50 mt-6 max-w-2xl mx-auto">
				Browse reports by category or search by name or attribute. Download as many reports as you need. Starting at
				<a href="/pricing" class="text-electric hover:text-electric-light">$299/month</a>. Cancel any time.
			</p>
		</div>

		<div class="space-y-4">
			{#each categories as cat}
				<div class="glass rounded-2xl p-6 sm:p-8 group hover:border-white/10 transition-all">
					<div class="flex items-start gap-4 sm:gap-6">
						<div class="w-12 h-12 sm:w-14 sm:h-14 shrink-0 rounded-xl bg-{cat.color}/10 flex items-center justify-center">
							<span class="text-2xl">{cat.icon}</span>
						</div>
						<div class="flex-1">
							<h2 class="text-white font-semibold text-lg sm:text-xl mb-2">{cat.name}</h2>
							<p class="text-sm text-white/50 leading-relaxed">{cat.desc}</p>
						</div>
						<a
							href="https://simplexbi.com/products/"
							class="hidden sm:flex items-center gap-2 shrink-0 px-4 py-2 glass glass-hover rounded-lg text-sm text-white/60 hover:text-white transition-all"
						>
							Browse
							<svg class="w-4 h-4" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2"><path d="M13 7l5 5m0 0l-5 5m5-5H6"/></svg>
						</a>
					</div>
				</div>
			{/each}
		</div>

		<div class="mt-12 text-center">
			<a
				href="https://simplexbi.com/products/"
				class="inline-flex items-center gap-2 px-8 py-4 bg-electric hover:bg-electric-light text-white font-semibold rounded-xl transition-all hover:shadow-xl hover:shadow-electric/20 text-base"
			>
				Browse Full Catalog
				<svg class="w-5 h-5" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2"><path d="M13 7l5 5m0 0l-5 5m5-5H6"/></svg>
			</a>
		</div>
	</div>
</section>

<div class="h-16 lg:hidden"></div>
