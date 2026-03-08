<section class="py-20 sm:py-28 relative">
	<div class="absolute inset-0 bg-gradient-to-b from-transparent via-electric/[0.02] to-transparent"></div>
	<div class="relative max-w-4xl mx-auto px-4 sm:px-6">
		<div class="text-center mb-14">
			<span class="text-xs font-semibold uppercase tracking-wider text-electric/80">What You Get</span>
			<h2 class="text-3xl sm:text-4xl lg:text-5xl font-bold text-white mt-4 leading-tight">
				Everything your firm needs.<br/>
				<span class="text-white/40">Nothing it doesn't.</span>
			</h2>
		</div>

		<div class="space-y-4">
			{#each features as feature, i}
				<div class="glass rounded-2xl p-5 sm:p-6 flex items-start gap-4 group hover:border-white/10 transition-all">
					<div class="w-10 h-10 shrink-0 rounded-xl bg-electric/10 flex items-center justify-center text-electric font-bold text-sm">
						{i + 1}
					</div>
					<div>
						<h3 class="text-white font-semibold text-base sm:text-lg mb-1">{feature.title}</h3>
						<p class="text-sm text-white/50 leading-relaxed">{feature.description}</p>
					</div>
				</div>
			{/each}
		</div>

		<div class="mt-10 text-center">
			<p class="text-white/40 text-sm">All of this for a fraction of the cost of a single custom report.</p>
		</div>
	</div>
</section>

<script lang="ts">
	const features = [
		{
			title: 'Full Report Library Access',
			description: 'A growing collection of pre-built SSRS reports that solve common law firm reporting challenges.'
		},
		{
			title: 'New Reports Added Monthly',
			description: 'Stay ahead with fresh insights and tools to simplify your workflows, driven by community needs.'
		},
		{
			title: 'Organized, Searchable Catalog',
			description: 'Quickly find the right report for your needs with a clear, intuitive catalog organized by category.'
		},
		{
			title: 'Flexible Subscription Tiers',
			description: 'Choose the level that best fits your firm — whether you need ready-to-use reports or customized support.'
		},
		{
			title: 'Custom Reporting Support',
			description: 'Need a tailored solution? Our team is here to help with custom report development and configuration.'
		}
	];
</script>
