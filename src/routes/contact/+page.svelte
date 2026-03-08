<svelte:head>
	<title>Contact — Simplex BI</title>
	<meta name="description" content="Get in touch with Simplex BI. We'd love to hear from you about FirmFocus, consulting services, or any Aderant questions." />
</svelte:head>

<section class="pt-28 sm:pt-36 pb-20 sm:pb-28 relative">
	<div class="absolute inset-0 grid-bg"></div>
	<div class="absolute top-0 left-1/2 -translate-x-1/2 w-[600px] h-[400px] bg-electric/5 rounded-full blur-[120px]"></div>

	<div class="relative max-w-4xl mx-auto px-4 sm:px-6">
		<div class="text-center mb-14">
			<span class="text-xs font-semibold uppercase tracking-wider text-electric/80">Contact Us</span>
			<h1 class="text-4xl sm:text-5xl lg:text-6xl font-bold text-white mt-4 leading-tight">
				Let's talk.
			</h1>
			<p class="text-lg text-white/50 mt-6 max-w-xl mx-auto">
				Whether you're interested in FirmFocus, consulting services, or just have a question — we'd love to hear from you.
			</p>
		</div>

		<div class="grid grid-cols-1 lg:grid-cols-5 gap-6">
			<!-- Contact Form -->
			<div class="lg:col-span-3 glass rounded-2xl p-6 sm:p-8">
				<form
					action="https://simplexbi.com/contact/"
					method="GET"
					class="space-y-5"
				>
					<div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
						<div>
							<label for="firstName" class="block text-sm text-white/60 mb-1.5">First Name</label>
							<input
								type="text"
								id="firstName"
								name="firstName"
								class="w-full px-4 py-3 bg-white/5 border border-white/10 rounded-xl text-white text-sm placeholder-white/30 focus:outline-none focus:border-electric/40 focus:ring-1 focus:ring-electric/20 transition-all"
								placeholder="Ivan"
							/>
						</div>
						<div>
							<label for="lastName" class="block text-sm text-white/60 mb-1.5">Last Name</label>
							<input
								type="text"
								id="lastName"
								name="lastName"
								class="w-full px-4 py-3 bg-white/5 border border-white/10 rounded-xl text-white text-sm placeholder-white/30 focus:outline-none focus:border-electric/40 focus:ring-1 focus:ring-electric/20 transition-all"
								placeholder="Stokotelny"
							/>
						</div>
					</div>

					<div>
						<label for="company" class="block text-sm text-white/60 mb-1.5">Company Name</label>
						<input
							type="text"
							id="company"
							name="company"
							class="w-full px-4 py-3 bg-white/5 border border-white/10 rounded-xl text-white text-sm placeholder-white/30 focus:outline-none focus:border-electric/40 focus:ring-1 focus:ring-electric/20 transition-all"
							placeholder="Your Firm"
						/>
					</div>

					<div>
						<label for="email" class="block text-sm text-white/60 mb-1.5">Email Address</label>
						<input
							type="email"
							id="email"
							name="email"
							class="w-full px-4 py-3 bg-white/5 border border-white/10 rounded-xl text-white text-sm placeholder-white/30 focus:outline-none focus:border-electric/40 focus:ring-1 focus:ring-electric/20 transition-all"
							placeholder="you@firm.com"
						/>
					</div>

					<div>
						<label for="message" class="block text-sm text-white/60 mb-1.5">Message</label>
						<textarea
							id="message"
							name="message"
							rows="4"
							class="w-full px-4 py-3 bg-white/5 border border-white/10 rounded-xl text-white text-sm placeholder-white/30 focus:outline-none focus:border-electric/40 focus:ring-1 focus:ring-electric/20 transition-all resize-none"
							placeholder="Tell us about your needs..."
						></textarea>
					</div>

					<button
						type="submit"
						class="w-full py-3.5 bg-electric hover:bg-electric-light text-white font-semibold rounded-xl transition-all hover:shadow-xl hover:shadow-electric/20"
					>
						Send Message
					</button>
				</form>
			</div>

			<!-- Contact Info -->
			<div class="lg:col-span-2 space-y-4">
				<div class="glass rounded-2xl p-6">
					<h3 class="text-white font-semibold text-sm mb-3">Phone</h3>
					<a href="tel:+16102557245" class="text-electric hover:text-electric-light text-lg font-medium transition-colors">
						(610) 255-7245
					</a>
				</div>

				<div class="glass rounded-2xl p-6">
					<h3 class="text-white font-semibold text-sm mb-3">Email</h3>
					<a href="mailto:info@simplexbi.com" class="text-electric hover:text-electric-light text-base font-medium transition-colors">
						info@simplexbi.com
					</a>
				</div>

				<div class="glass rounded-2xl p-6">
					<h3 class="text-white font-semibold text-sm mb-3">Office</h3>
					<p class="text-white/50 text-sm leading-relaxed">
						303 W. Lancaster Ave.<br/>
						Suite 270<br/>
						Wayne, PA 19087
					</p>
				</div>

				<div class="glass rounded-2xl p-6">
					<h3 class="text-white font-semibold text-sm mb-3">Social</h3>
					<div class="flex items-center gap-3">
						<a href="https://www.linkedin.com/company/simplex-bi" class="text-white/40 hover:text-electric transition-colors" aria-label="LinkedIn">
							<svg class="w-5 h-5" fill="currentColor" viewBox="0 0 24 24"><path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433a2.062 2.062 0 01-2.063-2.065 2.064 2.064 0 112.063 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/></svg>
						</a>
						<a href="https://twitter.com/simplexbi" class="text-white/40 hover:text-electric transition-colors" aria-label="Twitter">
							<svg class="w-5 h-5" fill="currentColor" viewBox="0 0 24 24"><path d="M18.244 2.25h3.308l-7.227 8.26 8.502 11.24H16.17l-5.214-6.817L4.99 21.75H1.68l7.73-8.835L1.254 2.25H8.08l4.713 6.231zm-1.161 17.52h1.833L7.084 4.126H5.117z"/></svg>
						</a>
					</div>
				</div>
			</div>
		</div>
	</div>
</section>

<div class="h-16 lg:hidden"></div>
