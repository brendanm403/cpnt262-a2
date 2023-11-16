<script>
	import '../../app.postcss';
	import { AppShell, AppBar, Avatar, LightSwitch } from '@skeletonlabs/skeleton';

	let navLinks = [
		{name: "Home", href: "/"},
		{name: "About", href: "/about"},
		{name: "Products", href: "/products"}
	]
</script>

<slot />

<AppShell>
	<svelte:fragment slot="header">
    <AppBar>
      <svelte:fragment slot="lead"><Avatar src="https://images.unsplash.com/photo-1617296538902-887900d9b592?ixid=M3w0Njc5ODF8MHwxfGFsbHx8fHx8fHx8fDE2ODc5NzExMDB8&ixlib=rb-4.0.3&w=128&h=128&auto=format&fit=crop" width="w-10" rounded="rounded-full" initials="BM" border="border-4 border-surface-300-600-token hover:!border-primary-500"
      cursor="cursor-pointer"/></svelte:fragment>
      <h2 class="text-2xl">Site Title</h2>
      <svelte:fragment slot="trail">
      
        <nav>
          <ul class="flex">
            {#each navLinks as {name, href}}
              <li class="mx-5"><a class="p-2" {href}>{name}</a></li>
            {/each}
          </ul>
        </nav>
        
        <LightSwitch class="mx-2"/>
      </svelte:fragment>
    </AppBar>
  </svelte:fragment>
	<!-- (sidebarLeft) -->
	<!-- (sidebarRight) -->
	<svelte:fragment slot="pageHeader">Page Header</svelte:fragment>
	<!-- Router Slot -->
	<slot />
	<!-- ---- / ---- -->
	<svelte:fragment slot="pageFooter">Page Footer</svelte:fragment>
	<!-- (footer) -->
</AppShell>