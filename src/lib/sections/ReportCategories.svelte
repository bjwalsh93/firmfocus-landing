<section class="py-20 sm:py-28 relative">
	<div class="max-w-6xl mx-auto px-4 sm:px-6">
		<div class="text-center mb-14">
			<span class="text-xs font-semibold uppercase tracking-wider text-electric/80">Report Library</span>
			<h2 class="text-3xl sm:text-4xl lg:text-5xl font-bold text-white mt-4">
				24 reports. Six categories.<br/>
				<span class="text-white/40">Growing every month.</span>
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
						<h3 class="text-white font-semibold text-sm sm:text-base mb-0.5">{cat.name}</h3>
						<p class="text-[10px] text-white/30 mb-1">{cat.count} reports</p>
						<p class="text-xs text-white/40 leading-relaxed hidden sm:block">{cat.desc}</p>
					</div>
				</a>
			{/each}
		</div>

		<div class="text-center mt-10">
			<a
				href="/reports"
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
			count: 5,
			desc: 'Hours, amounts, utilization, and missing time analysis by timekeeper.',
			icon: '⏱',
			bg: 'bg-electric/10',
			glow: 'bg-electric/10'
		},
		{
			name: 'Client / Matter',
			count: 5,
			desc: 'Billable hours, billed amounts, write-offs, and worked/billed/collected by professional.',
			icon: '📋',
			bg: 'bg-accent-emerald/10',
			glow: 'bg-accent-emerald/10'
		},
		{
			name: 'Inventory',
			count: 4,
			desc: 'WIP aging, AR aging, credit balances, and open invoices.',
			icon: '📊',
			bg: 'bg-accent-cyan/10',
			glow: 'bg-accent-cyan/10'
		},
		{
			name: 'Matter Listings',
			count: 3,
			desc: 'New matters, participation splits, and missing split identification.',
			icon: '📁',
			bg: 'bg-purple-400/10',
			glow: 'bg-purple-400/10'
		},
		{
			name: 'Trust',
			count: 2,
			desc: 'Trust balances and transaction detail for compliance.',
			icon: '🔒',
			bg: 'bg-amber-400/10',
			glow: 'bg-amber-400/10'
		},
		{
			name: 'Utilities',
			count: 2,
			desc: 'Prebill and AP invoice lock troubleshooting reports.',
			icon: '⚙️',
			bg: 'bg-rose-400/10',
			glow: 'bg-rose-400/10'
		}
	];
</script>
