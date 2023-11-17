<script>
	import '../../app.postcss';
	import { AppShell, AppBar, Avatar, LightSwitch, ListBox, ListBoxItem } from '@skeletonlabs/skeleton';
  import PageHeader from "$lib/components/PageHeader.svelte";

	let navLinks = [
		{name: "Home", href: "/"},
		{name: "About", href: "/about"},
		{name: "Products", href: "/products"}
	]

  let valueSingle = 'books';
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
	<svelte:fragment slot="pageHeader">
    <PageHeader />
  </svelte:fragment>

  <h2 class="text-2xl text-center mt-5">Filter Products</h2>

  <ListBox class="w-1/5 mx-auto mt-5 bg-surface-200-700-token" rounded="rounded-container-token">
    <ListBoxItem bind:group={valueSingle} name="medium" value="books">Category 1</ListBoxItem>
    <ListBoxItem bind:group={valueSingle} name="medium" value="movies">Category 2</ListBoxItem>
    <ListBoxItem bind:group={valueSingle} name="medium" value="tv">Category 3</ListBoxItem>
  </ListBox>
			
	<!-- Router Slot -->
	<slot />
	<!-- ---- / ---- -->
	<svelte:fragment slot="pageFooter">Page Footer</svelte:fragment>
	<!-- (footer) -->
</AppShell>