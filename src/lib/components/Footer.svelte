<script lang="ts">
	const year = new Date().getFullYear();
</script>

<footer class="border-t border-white/5 bg-navy-950">
	<div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-16">
		<div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-10">
			<!-- Brand -->
			<div class="sm:col-span-2 lg:col-span-1">
				<div class="flex items-center gap-2 mb-4">
					<div class="w-8 h-8 rounded-lg bg-electric/10 border border-electric/20 flex items-center justify-center">
						<span class="text-electric font-bold text-sm">F</span>
					</div>
					<div>
						<div class="text-white font-semibold text-sm">FirmFocus</div>
						<div class="text-white/40 text-[10px]">by Simplex BI</div>
					</div>
				</div>
				<p class="text-white/40 text-sm leading-relaxed max-w-xs">
					Pre-built financial reports for Aderant Expert. 50+ years of combined legal tech expertise, delivered as a subscription.
				</p>
			</div>

			<!-- Product -->
			<div>
				<h4 class="text-white/60 text-xs font-semibold uppercase tracking-wider mb-4">Product</h4>
				<div class="space-y-3">
					<a href="/reports" class="block text-sm text-white/40 hover:text-white transition-colors">Report Library</a>
					<a href="/pricing" class="block text-sm text-white/40 hover:text-white transition-colors">Pricing</a>
					<a href="https://simplexbi.com/products/" class="block text-sm text-white/40 hover:text-white transition-colors">Browse Reports</a>
				</div>
			</div>

			<!-- Company -->
			<div>
				<h4 class="text-white/60 text-xs font-semibold uppercase tracking-wider mb-4">Company</h4>
				<div class="space-y-3">
					<a href="/about" class="block text-sm text-white/40 hover:text-white transition-colors">About Us</a>
					<a href="/services" class="block text-sm text-white/40 hover:text-white transition-colors">Services</a>
					<a href="/contact" class="block text-sm text-white/40 hover:text-white transition-colors">Contact</a>
				</div>
			</div>

			<!-- Contact Info -->
			<div>
				<h4 class="text-white/60 text-xs font-semibold uppercase tracking-wider mb-4">Get in Touch</h4>
				<div class="space-y-3 text-sm text-white/40">
					<p>(610) 255-7245</p>
					<p>info@simplexbi.com</p>
					<p>303 W. Lancaster Ave.<br />Suite 270<br />Wayne, PA 19087</p>
				</div>
			</div>
		</div>

		<div class="mt-12 pt-8 border-t border-white/5 flex flex-col sm:flex-row items-center justify-between gap-4">
			<p class="text-white/30 text-xs">&copy; {year} Simplex BI, Inc. All rights reserved.</p>
			<div class="flex items-center gap-6">
				<a href="https://simplexbi.com" class="text-white/30 hover:text-white/60 text-xs transition-colors">SimplexBI.com</a>
				<a href="https://www.linkedin.com/company/simplex-bi" class="text-white/30 hover:text-white/60 transition-colors" aria-label="LinkedIn">
					<svg class="w-4 h-4" fill="currentColor" viewBox="0 0 24 24"><path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433a2.062 2.062 0 01-2.063-2.065 2.064 2.064 0 112.063 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/></svg>
				</a>
			</div>
		</div>
	</div>
</footer>
