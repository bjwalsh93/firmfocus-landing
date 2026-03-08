<script lang="ts">
	let annual = $state(false);

	const plans = [
		{
			name: 'Essentials',
			monthlyPrice: 299,
			annualPrice: 2870,
			description: 'The perfect starting point for firms looking to streamline their Aderant reporting process.',
			features: [
				'Full access to our pre-built financial report library',
				'Immediate downloads for fast implementation',
				'Organized, searchable catalog for easy report discovery',
				'New reports added monthly to keep your insights up to date'
			],
			whoFor: 'Firms that need actionable, ready-to-use financial reports without the time or cost of custom development.',
			href: 'https://simplexbi.com/subscriptions/'
		},
		{
			name: 'Professional',
			monthlyPrice: 599,
			annualPrice: 5750,
			description: 'Take your reporting to the next level with additional customization and setup support.',
			features: [
				'Everything included in Essentials',
				'Installation and setup support — seamless implementation',
				'Cosmetic changes to reflect your firm\'s branding',
				'Priority email support'
			],
			whoFor: 'Firms seeking tailored reporting solutions with a professional, branded presentation — without the technical headaches.',
			popular: true,
			href: 'https://simplexbi.com/subscriptions/'
		},
		{
			name: 'Enterprise',
			monthlyPrice: 799,
			annualPrice: 7670,
			description: 'Our most comprehensive subscription — advanced features, full support, and custom reporting.',
			features: [
				'Everything included in Professional',
				'Custom reports designed specifically for your firm\'s unique needs',
				'Scheduled reports — automated delivery for consistent, timely insights',
				'EA Pro access and security setup'
			],
			whoFor: 'Firms looking for a robust, hands-on reporting solution with advanced features and dedicated customization.',
			href: 'https://simplexbi.com/subscriptions/'
		}
	];
</script>

<svelte:head>
	<title>Pricing — FirmFocus by Simplex BI</title>
	<meta name="description" content="FirmFocus subscription plans starting at $299/mo. Access a full library of pre-built Aderant reports for less than the cost of one custom report." />
</svelte:head>

<section class="pt-28 sm:pt-36 pb-20 sm:pb-28 relative">
	<div class="absolute inset-0 grid-bg"></div>
	<div class="absolute top-0 left-1/2 -translate-x-1/2 w-[600px] h-[400px] bg-electric/5 rounded-full blur-[120px]"></div>

	<div class="relative max-w-6xl mx-auto px-4 sm:px-6">
		<div class="text-center mb-14">
			<h1 class="text-4xl sm:text-5xl lg:text-6xl font-bold text-white leading-tight">
				Choose the Right Plan<br/>
				<span class="gradient-text">for Your Firm</span>
			</h1>
			<p class="text-lg text-white/50 mt-6 max-w-2xl mx-auto">
				Flexible subscription tiers to meet your firm's specific needs. Cancel anytime.
			</p>
		</div>

		<!-- Toggle -->
		<div class="flex items-center justify-center gap-3 mb-12">
			<span class="text-sm {annual ? 'text-white/40' : 'text-white font-medium'}">Monthly</span>
			<button
				onclick={() => (annual = !annual)}
				class="relative w-12 h-6 rounded-full transition-colors {annual ? 'bg-electric' : 'bg-white/10'}"
				aria-label="Toggle annual pricing"
			>
				<div class="absolute top-0.5 left-0.5 w-5 h-5 bg-white rounded-full transition-transform {annual ? 'translate-x-6' : ''}"></div>
			</button>
			<span class="text-sm {annual ? 'text-white font-medium' : 'text-white/40'}">
				Annual <span class="text-accent-emerald text-xs font-medium">Save 20%</span>
			</span>
		</div>

		<!-- Plans -->
		<div class="grid grid-cols-1 sm:grid-cols-3 gap-4 sm:gap-6">
			{#each plans as plan}
				<div
					class="glass rounded-2xl p-6 sm:p-8 relative {plan.popular
						? 'border-electric/30 glow-blue'
						: ''} flex flex-col"
				>
					{#if plan.popular}
						<div class="absolute -top-3 left-1/2 -translate-x-1/2 px-3 py-1 bg-electric text-white text-xs font-semibold rounded-full">
							Most Popular
						</div>
					{/if}

					<div class="mb-6">
						<h2 class="text-white font-semibold text-xl">{plan.name}</h2>
						<div class="mt-4">
							<span class="text-5xl font-bold text-white">
								${annual ? Math.round(plan.annualPrice / 12) : plan.monthlyPrice}
							</span>
							<span class="text-white/40 text-lg">/mo</span>
						</div>
						{#if annual}
							<p class="text-sm text-white/30 mt-1">${plan.annualPrice.toLocaleString()}/yr billed annually</p>
						{/if}
						<p class="text-sm text-white/50 mt-4 leading-relaxed">{plan.description}</p>
					</div>

					<ul class="space-y-3 mb-8 flex-1">
						{#each plan.features as feature}
							<li class="flex items-start gap-2">
								<svg class="w-4 h-4 text-electric shrink-0 mt-0.5" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2"><path d="M5 13l4 4L19 7"/></svg>
								<span class="text-sm text-white/60">{feature}</span>
							</li>
						{/each}
					</ul>

					<!-- Who it's for -->
					<div class="glass rounded-xl p-4 mb-6">
						<p class="text-xs text-white/40 uppercase tracking-wider font-semibold mb-1">Who it's for</p>
						<p class="text-sm text-white/60 leading-relaxed">{plan.whoFor}</p>
					</div>

					<a
						href={plan.href}
						class="block text-center py-3.5 rounded-xl font-medium transition-all {plan.popular
							? 'bg-electric hover:bg-electric-light text-white shadow-lg shadow-electric/20'
							: 'glass glass-hover text-white/80 hover:text-white'}"
					>
						Get Started
					</a>
				</div>
			{/each}
		</div>

		<!-- Add-on -->
		<div class="mt-12 glass rounded-2xl p-6 sm:p-8 text-center max-w-2xl mx-auto">
			<h3 class="text-white font-semibold text-lg mb-2">Optional Setup Assistance — $150 (one-time)</h3>
			<p class="text-sm text-white/50 leading-relaxed">
				Need help getting started? Our team can assist with setup and provide training to ensure you get the most out of your reports.
			</p>
		</div>

		<!-- Why Subscribe -->
		<div class="mt-16 max-w-3xl mx-auto">
			<h3 class="text-2xl font-bold text-white text-center mb-8">Why Subscribe?</h3>
			<div class="grid grid-cols-1 sm:grid-cols-3 gap-4">
				<div class="glass rounded-2xl p-6 text-center">
					<div class="text-2xl font-bold text-accent-emerald mb-2">Grow</div>
					<p class="text-sm text-white/50">New reports added monthly, driven by the Aderant community's needs.</p>
				</div>
				<div class="glass rounded-2xl p-6 text-center">
					<div class="text-2xl font-bold text-electric mb-2">Save</div>
					<p class="text-sm text-white/50">Access the full library for less than the cost of a single custom report.</p>
				</div>
				<div class="glass rounded-2xl p-6 text-center">
					<div class="text-2xl font-bold text-accent-cyan mb-2">Speed</div>
					<p class="text-sm text-white/50">Pre-built reports deliver immediate insights without manual effort.</p>
				</div>
			</div>
		</div>
	</div>
</section>

<!-- Bottom padding for mobile CTA bar -->
<div class="h-16 lg:hidden"></div>
