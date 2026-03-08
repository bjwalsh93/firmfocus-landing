<script lang="ts">
	let annual = $state(false);

	const plans = [
		{
			name: 'Essentials',
			monthlyPrice: 299,
			annualPrice: 2870,
			description: 'The perfect starting point for firms looking to streamline their Aderant reporting.',
			features: [
				'Full access to pre-built report library',
				'Immediate downloads',
				'Organized, searchable catalog',
				'New reports added monthly'
			],
			cta: 'Get Started',
			href: 'https://simplexbi.com/subscriptions/',
			accent: 'electric'
		},
		{
			name: 'Professional',
			monthlyPrice: 599,
			annualPrice: 5750,
			description: 'Customization and setup support for a professional, branded experience.',
			features: [
				'Everything in Essentials',
				'Installation & setup support',
				'Cosmetic changes & branding',
				'Priority assistance'
			],
			cta: 'Get Started',
			href: 'https://simplexbi.com/subscriptions/',
			popular: true,
			accent: 'accent-cyan'
		},
		{
			name: 'Enterprise',
			monthlyPrice: 799,
			annualPrice: 7670,
			description: 'Advanced features, full support, and custom reporting for complex needs.',
			features: [
				'Everything in Professional',
				'Custom reports for your firm',
				'Scheduled report delivery',
				'EA Pro access & security setup'
			],
			cta: 'Get Started',
			href: 'https://simplexbi.com/subscriptions/',
			accent: 'purple-400'
		}
	];
</script>

<section id="pricing" class="py-20 sm:py-28 relative">
	<div class="max-w-6xl mx-auto px-4 sm:px-6">
		<div class="text-center mb-14">
			<span class="text-xs font-semibold uppercase tracking-wider text-electric/80">Pricing</span>
			<h2 class="text-3xl sm:text-4xl lg:text-5xl font-bold text-white mt-4 leading-tight">
				One custom report: $10,000+<br/>
				<span class="gradient-text">FirmFocus: $299/mo for the whole library.</span>
			</h2>
		</div>

		<!-- Toggle -->
		<div class="flex items-center justify-center gap-3 mb-10">
			<span class="text-sm {annual ? 'text-white/40' : 'text-white'}">Monthly</span>
			<button
				onclick={() => (annual = !annual)}
				class="relative w-12 h-6 rounded-full transition-colors {annual ? 'bg-electric' : 'bg-white/10'}"
				aria-label="Toggle annual pricing"
			>
				<div class="absolute top-0.5 left-0.5 w-5 h-5 bg-white rounded-full transition-transform {annual ? 'translate-x-6' : ''}"></div>
			</button>
			<span class="text-sm {annual ? 'text-white' : 'text-white/40'}">
				Annual <span class="text-accent-emerald text-xs font-medium">Save 20%</span>
			</span>
		</div>

		<!-- Cards -->
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
						<h3 class="text-white font-semibold text-lg">{plan.name}</h3>
						<div class="mt-3">
							<span class="text-4xl font-bold text-white">
								${annual ? Math.round(plan.annualPrice / 12) : plan.monthlyPrice}
							</span>
							<span class="text-white/40 text-sm">/mo</span>
						</div>
						{#if annual}
							<p class="text-xs text-white/30 mt-1">${plan.annualPrice.toLocaleString()}/yr billed annually</p>
						{/if}
						<p class="text-sm text-white/50 mt-3 leading-relaxed">{plan.description}</p>
					</div>

					<ul class="space-y-3 mb-8 flex-1">
						{#each plan.features as feature}
							<li class="flex items-start gap-2">
								<svg class="w-4 h-4 text-electric shrink-0 mt-0.5" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2"><path d="M5 13l4 4L19 7"/></svg>
								<span class="text-sm text-white/60">{feature}</span>
							</li>
						{/each}
					</ul>

					<a
						href={plan.href}
						class="block text-center py-3 rounded-xl font-medium text-sm transition-all {plan.popular
							? 'bg-electric hover:bg-electric-light text-white shadow-lg shadow-electric/20'
							: 'glass glass-hover text-white/80 hover:text-white'}"
					>
						{plan.cta}
					</a>
				</div>
			{/each}
		</div>

		<!-- Add-on -->
		<div class="mt-6 text-center">
			<p class="text-white/30 text-sm">
				Need help getting started? <span class="text-white/50">Setup assistance available for a one-time $150 fee.</span>
			</p>
		</div>

		<div class="text-center mt-8">
			<a href="/pricing" class="inline-flex items-center gap-2 text-electric hover:text-electric-light text-sm font-medium transition-colors">
				View full plan details
				<svg class="w-4 h-4" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2"><path d="M13 7l5 5m0 0l-5 5m5-5H6"/></svg>
			</a>
		</div>
	</div>
</section>
