<script lang="ts">
	type Report = {
		code: string;
		name: string;
		description: string;
		sampleUrl?: string;
		comingSoon?: boolean;
	};

	type Category = {
		name: string;
		slug: string;
		icon: string;
		color: string;
		glowColor: string;
		reports: Report[];
	};

	let expandedCategory = $state<string | null>(null);

	function toggleCategory(slug: string) {
		expandedCategory = expandedCategory === slug ? null : slug;
	}

	const categories: Category[] = [
		{
			name: 'Working Timekeeper Reports',
			slug: 'timekeeper',
			icon: '⏱',
			color: 'text-electric',
			glowColor: 'bg-electric',
			reports: [
				{
					code: 'TK001',
					name: 'Timekeeper Hours and Amounts',
					description: 'Hours and amounts of time worked by Working Timekeeper MTD and YTD. Shows attorney utilization and can be used to reallocate workload or for annual compensation statistics.',
					sampleUrl: 'https://simplexbi.com/sample-timekeeper-hours-and-amounts/'
				},
				{
					code: 'TK002',
					name: 'Timekeeper Hours and Amounts Detail',
					description: 'Detailed breakdown of timekeeper hours and amounts with client/matter-level granularity.'
				},
				{
					code: 'TK003',
					name: 'Timekeeper Total Hours Summary',
					description: 'Summary view of total hours across all timekeepers for quick firm-wide utilization analysis.'
				},
				{
					code: 'TK004',
					name: 'Timekeeper Total Hours Detail',
					description: 'Detailed total hours report with drill-down into individual timekeeper activity.'
				},
				{
					code: 'TK005',
					name: 'Timekeeper Missing Time',
					description: 'Identifies timekeepers with missing or incomplete time entries to ensure billing accuracy.'
				}
			]
		},
		{
			name: 'Client/Matter Reports (By Professional)',
			slug: 'client-matter',
			icon: '📋',
			color: 'text-accent-emerald',
			glowColor: 'bg-accent-emerald',
			reports: [
				{
					code: 'CM001',
					name: 'Billable Hours and Amounts',
					description: 'Hours and amounts of time worked by Billing Timekeeper MTD and YTD. Analyze production by individual attorneys with client/matter detail.',
				},
				{
					code: 'CM002',
					name: 'Billed Amounts Detail',
					description: 'Detailed breakdown of billed amounts by professional, showing where revenue is being generated.'
				},
				{
					code: 'CM003',
					name: 'AR Write-Offs',
					description: 'Accounts receivable write-off analysis by professional to track and manage revenue leakage.'
				},
				{
					code: 'CM004',
					name: 'Summary of Client Matter Activity',
					description: 'Consolidated view of all financial activity across client matters for each billing professional.'
				},
				{
					code: 'CM005',
					name: 'Worked, Billed, Collected',
					description: 'Value worked, billed, and collected by MTD and YTD. The essential financial activity view for every matter.',
					comingSoon: true
				}
			]
		},
		{
			name: 'Inventory By Professional',
			slug: 'inventory',
			icon: '📊',
			color: 'text-accent-cyan',
			glowColor: 'bg-accent-cyan',
			reports: [
				{
					code: 'IN001',
					name: 'WIP Aging',
					description: 'Work-in-progress aging analysis to identify unbilled inventory and potential cash flow risks.',
					comingSoon: true
				},
				{
					code: 'IN002',
					name: 'Accounts Receivable Aging',
					description: 'AR aging buckets by professional to prioritize collections and manage outstanding balances.',
					comingSoon: true
				},
				{
					code: 'IN005',
					name: 'Credit Balances',
					description: 'Identifies client accounts with credit balances for proper trust management and reconciliation.',
					comingSoon: true
				},
				{
					code: 'IN006',
					name: 'Open Invoices',
					description: 'Complete listing of open invoices with aging detail for collections management.',
					comingSoon: true
				}
			]
		},
		{
			name: 'Matter Listings',
			slug: 'matters',
			icon: '📁',
			color: 'text-purple-400',
			glowColor: 'bg-purple-400',
			reports: [
				{
					code: 'ML001',
					name: 'New Matter Listing',
					description: 'New matters opened within a date range, showing office, department, billing/responsible timekeepers, status, and related parties.',
					sampleUrl: 'https://simplexbi.com/'
				},
				{
					code: 'ML002',
					name: 'Matters Missing Participation Splits',
					description: 'Identifies matters that are missing participation split assignments for accurate revenue attribution.',
					comingSoon: true
				},
				{
					code: 'ML003',
					name: 'Matter Participation Split Listing',
					description: 'Full listing of matter participation splits for compensation and profitability analysis.',
					comingSoon: true
				}
			]
		},
		{
			name: 'Trust',
			slug: 'trust',
			icon: '🔒',
			color: 'text-amber-400',
			glowColor: 'bg-amber-400',
			reports: [
				{
					code: 'TR001',
					name: 'Trust Balance Report',
					description: 'Current trust account balances across all client accounts for compliance monitoring.',
					comingSoon: true
				},
				{
					code: 'TR002',
					name: 'Trust Transaction Detail',
					description: 'Detailed trust account transaction history for auditing and reconciliation.',
					comingSoon: true
				}
			]
		},
		{
			name: 'Utilities',
			slug: 'utilities',
			icon: '⚙️',
			color: 'text-rose-400',
			glowColor: 'bg-rose-400',
			reports: [
				{
					code: 'UT001',
					name: 'Prebill Lock Report',
					description: 'Identifies the Transaction Uno associated with a specific prebill lock. Used when Aderant fails to release a lock, preventing users from editing and posting prebills.',
					sampleUrl: 'https://simplexbi.com/sample-prebill-lock-report/'
				},
				{
					code: 'UT002',
					name: 'AP Invoice Lock Report',
					description: 'Identifies locked AP invoices for troubleshooting and resolution.',
					comingSoon: true
				}
			]
		}
	];

	const totalReports = categories.reduce((sum, cat) => sum + cat.reports.length, 0);
	const availableNow = categories.reduce((sum, cat) => sum + cat.reports.filter(r => !r.comingSoon).length, 0);
</script>

<svelte:head>
	<title>Report Library — FirmFocus by Simplex BI</title>
	<meta name="description" content="Browse {totalReports} pre-built SSRS reports for Aderant Expert across 6 categories. Download instantly with a FirmFocus subscription." />
</svelte:head>

<section class="pt-28 sm:pt-36 pb-20 sm:pb-28 relative">
	<div class="absolute inset-0 grid-bg"></div>
	<div class="absolute top-0 left-1/2 -translate-x-1/2 w-[600px] h-[400px] bg-electric/5 rounded-full blur-[120px]"></div>

	<div class="relative max-w-5xl mx-auto px-4 sm:px-6">
		<!-- Header -->
		<div class="text-center mb-6">
			<h1 class="text-4xl sm:text-5xl lg:text-6xl font-bold text-white leading-tight">
				Report Library
			</h1>
			<p class="text-lg text-white/50 mt-6 max-w-2xl mx-auto">
				Browse reports by category. Download as many as you need. Starting at
				<a href="/pricing" class="text-electric hover:text-electric-light transition-colors">$299/month</a>. Cancel any time.
			</p>
		</div>

		<!-- Stats bar -->
		<div class="flex items-center justify-center gap-6 sm:gap-10 mb-14">
			<div class="text-center">
				<div class="text-2xl font-bold text-white">{totalReports}</div>
				<div class="text-xs text-white/40">Total Reports</div>
			</div>
			<div class="w-px h-8 bg-white/10"></div>
			<div class="text-center">
				<div class="text-2xl font-bold text-accent-emerald">{availableNow}</div>
				<div class="text-xs text-white/40">Available Now</div>
			</div>
			<div class="w-px h-8 bg-white/10"></div>
			<div class="text-center">
				<div class="text-2xl font-bold text-electric">6</div>
				<div class="text-xs text-white/40">Categories</div>
			</div>
		</div>

		<!-- Categories -->
		<div class="space-y-4">
			{#each categories as cat}
				<div class="glass rounded-2xl overflow-hidden transition-all">
					<!-- Category header -->
					<button
						onclick={() => toggleCategory(cat.slug)}
						class="w-full flex items-center gap-4 p-5 sm:p-6 text-left hover:bg-white/[0.02] transition-colors"
					>
						<div class="w-11 h-11 sm:w-12 sm:h-12 shrink-0 rounded-xl bg-white/5 flex items-center justify-center">
							<span class="text-xl sm:text-2xl">{cat.icon}</span>
						</div>
						<div class="flex-1 min-w-0">
							<h2 class="text-white font-semibold text-base sm:text-lg">{cat.name}</h2>
							<p class="text-xs text-white/40 mt-0.5">
								{cat.reports.length} report{cat.reports.length !== 1 ? 's' : ''}
								{#if cat.reports.some(r => r.comingSoon)}
									<span class="text-white/30">·</span>
									<span class="text-amber-400/70">{cat.reports.filter(r => r.comingSoon).length} coming soon</span>
								{/if}
							</p>
						</div>
						<svg
							class="w-5 h-5 text-white/30 shrink-0 transition-transform duration-200 {expandedCategory === cat.slug ? 'rotate-180' : ''}"
							fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2"
						>
							<path d="M19 9l-7 7-7-7" />
						</svg>
					</button>

					<!-- Expanded report list -->
					{#if expandedCategory === cat.slug}
						<div class="border-t border-white/5">
							{#each cat.reports as report, i}
								<div class="flex items-start gap-3 sm:gap-4 p-4 sm:px-6 sm:py-5 {i < cat.reports.length - 1 ? 'border-b border-white/[0.03]' : ''} hover:bg-white/[0.02] transition-colors">
									<!-- Report code badge -->
									<div class="shrink-0 mt-0.5">
										<span class="inline-block px-2 py-0.5 text-[10px] font-mono font-semibold rounded {report.comingSoon ? 'bg-amber-400/10 text-amber-400/70' : 'bg-electric/10 text-electric'}">{report.code}</span>
									</div>

									<!-- Report info -->
									<div class="flex-1 min-w-0">
										<div class="flex items-center gap-2 flex-wrap">
											<h3 class="text-white font-medium text-sm sm:text-base">{report.name}</h3>
											{#if report.comingSoon}
												<span class="px-1.5 py-0.5 text-[10px] rounded bg-amber-400/10 text-amber-400/70 font-medium whitespace-nowrap">Coming Soon</span>
											{/if}
										</div>
										<p class="text-xs sm:text-sm text-white/40 leading-relaxed mt-1">{report.description}</p>
										{#if report.sampleUrl && !report.comingSoon}
											<a
												href={report.sampleUrl}
												class="inline-flex items-center gap-1 mt-2 text-xs text-electric/70 hover:text-electric transition-colors"
											>
												<svg class="w-3 h-3" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2"><path d="M12 10v6m0 0l-3-3m3 3l3-3m2 8H7a2 2 0 01-2-2V5a2 2 0 012-2h5.586a1 1 0 01.707.293l5.414 5.414a1 1 0 01.293.707V19a2 2 0 01-2 2z"/></svg>
												View Sample
											</a>
										{/if}
									</div>

									<!-- Download / Subscribe -->
									{#if !report.comingSoon}
										<a
											href="https://simplexbi.com/product/{report.code.toLowerCase()}/"
											class="hidden sm:inline-flex shrink-0 items-center gap-1.5 px-3 py-1.5 glass glass-hover rounded-lg text-xs text-white/50 hover:text-white transition-all"
										>
											Details
											<svg class="w-3 h-3" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2"><path d="M9 5l7 7-7 7"/></svg>
										</a>
									{/if}
								</div>
							{/each}
						</div>
					{/if}
				</div>
			{/each}
		</div>

		<!-- Add-on callout -->
		<div class="mt-8 glass rounded-2xl p-5 sm:p-6 flex flex-col sm:flex-row items-start sm:items-center gap-4">
			<div class="flex-1">
				<h3 class="text-white font-semibold text-base">Need help getting set up?</h3>
				<p class="text-sm text-white/40 mt-1">Our team can assist with installation and provide training for a one-time $150 fee.</p>
			</div>
			<a
				href="/contact"
				class="shrink-0 px-5 py-2.5 glass glass-hover rounded-xl text-sm text-white/70 hover:text-white font-medium transition-all"
			>
				Get Setup Help
			</a>
		</div>

		<!-- Bottom CTA -->
		<div class="mt-12 text-center">
			<a
				href="https://simplexbi.com/subscriptions/"
				class="inline-flex items-center gap-2 px-8 py-4 bg-electric hover:bg-electric-light text-white font-semibold rounded-xl transition-all hover:shadow-xl hover:shadow-electric/20 text-base"
			>
				Subscribe & Start Downloading
				<svg class="w-5 h-5" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2"><path d="M13 7l5 5m0 0l-5 5m5-5H6"/></svg>
			</a>
			<p class="text-white/30 text-sm mt-4">New reports added monthly. Cancel anytime.</p>
		</div>
	</div>
</section>

<div class="h-16 lg:hidden"></div>
