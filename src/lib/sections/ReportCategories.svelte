<section class="py-20 sm:py-28 relative">
	<div class="max-w-6xl mx-auto px-4 sm:px-6">
		<div class="text-center mb-14">
			<span class="text-xs font-semibold uppercase tracking-wider text-electric/80">Report Library</span>
			<h2 class="text-3xl sm:text-4xl lg:text-5xl font-bold text-white mt-4">
				Six categories. Every angle covered.
			</h2>
			<p class="text-lg text-white/50 mt-4 max-w-2xl mx-auto">
				Browse reports by category, download what you need, deploy in minutes.
			</p>
		</div>

		<div class="grid grid-cols-2 lg:grid-cols-3 gap-3 sm:gap-4">
			{#each categories as cat}
				<a
					href="/reports"
					class="glass rounded-2xl p-5 sm:p-6 group hover:border-white/10 transition-all relative overflow-hidden"
				>
					<div class="absolute top-0 right-0 w-20 h-20 rounded-full blur-[40px] opacity-0 group-hover:opacity-100 transition-opacity {cat.glow}"></div>
					<div class="relative">
						<div class="w-10 h-10 rounded-xl {cat.bg} flex items-center justify-center mb-3">
							<span class="text-lg">{cat.icon}</span>
						</div>
						<h3 class="text-white font-semibold text-sm sm:text-base mb-1">{cat.name}</h3>
						<p class="text-xs text-white/40 leading-relaxed hidden sm:block">{cat.desc}</p>
					</div>
				</a>
			{/each}
		</div>

		<div class="text-center mt-10">
			<a
				href="https://simplexbi.com/products/"
				class="inline-flex items-center gap-2 text-electric hover:text-electric-light text-sm font-medium transition-colors"
			>
				Browse Full Report Catalog
				<svg class="w-4 h-4" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2"><path d="M13 7l5 5m0 0l-5 5m5-5H6"/></svg>
			</a>
		</div>
	</div>
</section>

<script lang="ts">
	const categories = [
		{
			name: 'Working Timekeeper',
			desc: 'Track billable hours, utilization rates, and timekeeper productivity across your firm.',
			icon: '⏱',
			bg: 'bg-electric/10',
			glow: 'bg-electric/10'
		},
		{
			name: 'Client / Matter',
			desc: 'Financial performance by professional — revenue, WIP, collections, and profitability.',
			icon: '📋',
			bg: 'bg-accent-emerald/10',
			glow: 'bg-accent-emerald/10'
		},
		{
			name: 'Inventory',
			desc: 'WIP and AR aging, unbilled inventory analysis, and collection forecasting.',
			icon: '📊',
			bg: 'bg-accent-cyan/10',
			glow: 'bg-accent-cyan/10'
		},
		{
			name: 'Matter Listings',
			desc: 'Comprehensive matter data views, status tracking, and matter lifecycle reporting.',
			icon: '📁',
			bg: 'bg-purple-400/10',
			glow: 'bg-purple-400/10'
		},
		{
			name: 'Trust',
			desc: 'Trust account balances, transactions, reconciliation, and compliance reporting.',
			icon: '🔒',
			bg: 'bg-amber-400/10',
			glow: 'bg-amber-400/10'
		},
		{
			name: 'Utilities',
			desc: 'System administration reports, data validation, and operational health checks.',
			icon: '⚙️',
			bg: 'bg-rose-400/10',
			glow: 'bg-rose-400/10'
		}
	];
</script>
