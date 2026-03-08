<script lang="ts">
	let openFaq = $state<string | null>(null);

	function toggleFaq(id: string) {
		openFaq = openFaq === id ? null : id;
	}

	const services = [
		{
			title: 'Consulting Services',
			subtitle: 'Law Firm Technology Consultants',
			description: 'A successful Aderant Expert implementation requires strong leadership. Simplex BI provides decades of legal industry and Aderant experience to guide your firm through the project life cycle, minimizing business risk and ensuring a successful go-live.',
			capabilities: [
				'Project Management', 'Test Plan Development', 'Workflow Design',
				'Consulting and Best Practices', 'Contract and SOW Review',
				'Add-On Module Implementations', 'Upgrade Management',
				'Go-Live Preparation & Support', 'Training and Rollout Plan',
				'Testing Assistance and Support'
			],
			faqs: [
				{
					id: 'c1',
					q: 'Do your services replace the services provided by Aderant?',
					a: 'No. Typically Simplex BI serves as your firm\'s internal project manager. There are certain tasks Aderant is better suited to perform such as data conversion and server installation but we will advise and assist with many configuration, testing, and training tasks.'
				},
				{
					id: 'c2',
					q: 'Is Simplex BI independent from Aderant?',
					a: 'Yes. We maintain a close working relationship with Aderant but ultimately we represent our client\'s interests in every aspect of an implementation.'
				},
				{
					id: 'c3',
					q: 'What is the best time to engage with Simplex BI?',
					a: 'Ideally, it is best to engage with us prior to signing an implementation or upgrade contract as we can provide valuable input to the contract and Statement of Work. However, we are often brought in after implementation has started and are happy to join your team at any point.'
				},
				{
					id: 'c4',
					q: 'Why do I need help with an upgrade?',
					a: 'If you are making a big jump in versions, there is a significant amount of testing that needs to be done. We can organize your team and ensure testing is completed and issues are resolved. Additionally, a big jump in versions can mean lots of new features and potentially applications you have not used previously.'
				}
			],
			accent: 'electric'
		},
		{
			title: 'Business Intelligence & Reporting',
			subtitle: 'Timely Access to Your Data',
			description: 'Access to data is critical to managing your firm. Simplex BI provides reporting strategy consulting and report development services to help keep firm leadership informed on the state of the business.',
			capabilities: [
				'Data Warehousing', 'Legacy Report Conversion',
				'SSRS Report Development and Automation', 'Delivery Strategy',
				'SSRS and Tables Training', 'Data Extractions',
				'Alerts', 'Dashboards'
			],
			faqs: [
				{
					id: 'b1',
					q: "Can't our internal staff write the reports we need?",
					a: 'In theory, yes. In practice, the challenge lies not in the technology, but with the lack of expertise with the Aderant database. A technical developer can code the reports, but will not be able to deliver output that requires business knowledge. Conversely, a financial analyst may possess the accounting skills, but lack the technical tools needed to create timely output.'
				},
				{
					id: 'b2',
					q: "Don't I get reporting when I purchase Aderant?",
					a: 'Yes. You get some essential inquiry and reporting out of the box, but most firms need more. Additionally, reporting tends to be an afterthought in the implementation. By the time attention is paid to the fact that there are reports missing, there is not enough time to create them all.'
				},
				{
					id: 'b3',
					q: 'How is Simplex able to deliver?',
					a: 'We follow a prescriptive approach while acknowledging that each Firm is unique. The needs of every Firm can differ in the requirements and methods. We take the time to understand your Firm\'s unique needs.'
				}
			],
			accent: 'accent-emerald'
		},
		{
			title: 'Custom Application Development',
			subtitle: 'Tailored Solutions for Your Firm',
			description: 'Do you have business requirements not addressed by available software? Simplex BI will design and develop custom software — from advanced FTE calculations and partner compensation tracking to third-party integrations and practice group-specific tools.',
			capabilities: [
				'Advanced FTE Calculations', 'Partner Compensation Tracking',
				'Attorney Evaluations', 'Report & Alert Management',
				'3rd Party Integrations', 'Practice Group Tools'
			],
			faqs: [
				{
					id: 'a1',
					q: 'Can you help us integrate with a 3rd party software?',
					a: 'Absolutely! We are happy to work with any other vendors in assisting them with moving your projects forward. Rely on us to provide the in-depth Aderant knowledge needed to integrate with your software investments.'
				},
				{
					id: 'a2',
					q: "Isn't it cheaper to buy software off the shelf?",
					a: 'Sometimes it is, and sometimes it isn\'t. As your trusted advisor, we start by evaluating each unique situation and advising the proper course of action. Sometimes there is an off the shelf solution. Other times the specific need can be easily solved by software designed specifically for your Firm.'
				}
			],
			accent: 'accent-cyan'
		}
	];
</script>

<svelte:head>
	<title>Services — Simplex BI</title>
	<meta name="description" content="Simplex BI consulting services: Aderant implementation, business intelligence & reporting, and custom application development for law firms." />
</svelte:head>

<section class="pt-28 sm:pt-36 pb-20 sm:pb-28 relative">
	<div class="absolute inset-0 grid-bg"></div>
	<div class="absolute top-0 left-1/2 -translate-x-1/2 w-[600px] h-[400px] bg-electric/5 rounded-full blur-[120px]"></div>

	<div class="relative max-w-4xl mx-auto px-4 sm:px-6">
		<div class="text-center mb-14">
			<span class="text-xs font-semibold uppercase tracking-wider text-electric/80">Simplex BI Services</span>
			<h1 class="text-4xl sm:text-5xl lg:text-6xl font-bold text-white mt-4 leading-tight">
				Expertise you can trust.
			</h1>
			<p class="text-lg text-white/50 mt-6 max-w-2xl mx-auto">
				Beyond FirmFocus, Simplex BI provides full-service consulting, reporting, and custom development for Aderant firms.
			</p>
		</div>

		<div class="space-y-6">
			{#each services as service}
				<div class="glass rounded-2xl overflow-hidden">
					<div class="p-6 sm:p-8">
						<div class="flex items-start gap-4 mb-4">
							<div class="w-2 h-12 rounded-full bg-{service.accent} shrink-0"></div>
							<div>
								<h2 class="text-white font-bold text-xl sm:text-2xl">{service.title}</h2>
								<p class="text-{service.accent} text-sm mt-1">{service.subtitle}</p>
							</div>
						</div>
						<p class="text-white/50 text-base leading-relaxed mb-6">{service.description}</p>

						<!-- Capabilities -->
						<div class="flex flex-wrap gap-2 mb-6">
							{#each service.capabilities as cap}
								<span class="px-3 py-1 text-xs text-white/50 glass rounded-full">{cap}</span>
							{/each}
						</div>

						<!-- FAQs -->
						<div class="space-y-2">
							{#each service.faqs as faq}
								<div class="glass rounded-xl overflow-hidden">
									<button
										onclick={() => toggleFaq(faq.id)}
										class="w-full flex items-center justify-between p-4 text-left"
									>
										<span class="text-sm text-white/70 font-medium pr-4">{faq.q}</span>
										<svg
											class="w-4 h-4 text-white/30 shrink-0 transition-transform {openFaq === faq.id ? 'rotate-180' : ''}"
											fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2"
										>
											<path d="M19 9l-7 7-7-7" />
										</svg>
									</button>
									{#if openFaq === faq.id}
										<div class="px-4 pb-4">
											<p class="text-sm text-white/40 leading-relaxed">{faq.a}</p>
										</div>
									{/if}
								</div>
							{/each}
						</div>
					</div>
				</div>
			{/each}
		</div>

		<div class="mt-12 text-center">
			<a
				href="/contact"
				class="inline-flex items-center gap-2 px-8 py-4 bg-electric hover:bg-electric-light text-white font-semibold rounded-xl transition-all hover:shadow-xl hover:shadow-electric/20 text-base"
			>
				Contact Us
			</a>
		</div>
	</div>
</section>

<div class="h-16 lg:hidden"></div>
