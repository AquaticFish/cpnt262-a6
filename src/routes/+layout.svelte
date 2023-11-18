<script>
	import '../app.postcss';
	import { AppShell, AppBar } from '@skeletonlabs/skeleton';

	import { LightSwitch } from '@skeletonlabs/skeleton';
</script>

<!-- App Shell -->
<AppShell>
	<svelte:fragment slot="header">
		<!-- App Bar -->
		<AppBar>
			<svelte:fragment slot="lead">
				<strong
				 class="text-xl uppercase">Hello</strong>
			</svelte:fragment>
			<svelte:fragment slot="trail">

			<LightSwitch />

			<a
			href="/"
			class="btn btn-sm variant-ghost-surface"
			rel="noreferrer"
		>
			Home
		</a>
			<a
				  href="/about"
					class="btn btn-sm variant-ghost-surface"
					rel="noreferrer"
				>
					About
				</a>
				<a
				  href="/gallery"
					class="btn btn-sm variant-ghost-surface"
					rel="noreferrer"
				>
					Gallery
				</a>
				<a
					href="/contact"
					class="btn btn-sm variant-ghost-surface"
					rel="noreferrer"
				>
					Contact
				</a>
			</svelte:fragment>
		</AppBar>
	</svelte:fragment>
	<!-- Page Route Content -->
	<slot />
</AppShell>

