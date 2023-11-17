<script>
	import '../../app.postcss';
	import { AppShell, AppBar, Avatar, LightSwitch, Accordion, AccordionItem, AppRail, AppRailTile, AppRailAnchor } from '@skeletonlabs/skeleton';
	import Icon from '@iconify/svelte';
	import {sectionData} from "$lib/home-data.js";
	import Section from "$lib/components/Section.svelte";
	let navLinks = [
		{name: "Home", href: "/"},
		{name: "About", href: "/about"},
		{name: "Products", href: "/products"}
	]

	let currentTile = 0;
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
	<h1 class="text-center text-5xl my-5">Main Page Heading</h1>
	<svelte:fragment slot="sidebarLeft">
		
<AppRail>
	<svelte:fragment slot="lead">
		<AppRailAnchor href="/" >(icon)</AppRailAnchor>
	</svelte:fragment>
	<!-- --- -->
	<AppRailTile bind:group={currentTile} name="tile-1" value={0} title="tile-1">
		<svelte:fragment slot="lead">(icon)</svelte:fragment>
		<span>Tile 1</span>
	</AppRailTile>
	<AppRailTile bind:group={currentTile} name="tile-2" value={1} title="tile-2">
		<svelte:fragment slot="lead">(icon)</svelte:fragment>
		<span>Tile 2</span>
	</AppRailTile>
	<AppRailTile bind:group={currentTile} name="tile-3" value={2} title="tile-3">
		<svelte:fragment slot="lead">(icon)</svelte:fragment>
		<span>Tile 3</span>
	</AppRailTile>
	<!-- --- -->
	<svelte:fragment slot="trail">
		<AppRailAnchor href="/" target="_blank" title="Account">(icon)</AppRailAnchor>
	</svelte:fragment>
</AppRail>

	</svelte:fragment>
	<Accordion class="mt-16 mx-auto" width="w-3/5">
		<AccordionItem open>
			<svelte:fragment slot="lead"><Icon icon="material-symbols:add-moderator" width="31" height="31" /></svelte:fragment>
			<svelte:fragment slot="summary"><h2 class="text-2xl">Section 1 Preview</h2></svelte:fragment>
			<svelte:fragment slot="content"><p>Lorem, ipsum dolor sit amet consectetur adipisicing elit. Iure delectus animi in expedita, amet voluptate tempora nobis eum optio dicta culpa, quas beatae nesciunt blanditiis? Lorem ipsum dolor sit amet consectetur adipisicing elit. Quas repudiandae consequuntur quae incidunt cumque modi?</p></svelte:fragment>
		</AccordionItem>
		<AccordionItem>
			<svelte:fragment slot="lead"><Icon icon="material-symbols:add-location-alt" width="31" height="31" /></svelte:fragment>
			<svelte:fragment slot="summary"><h2 class="text-2xl">Section 2 Preview</h2></svelte:fragment>
			<svelte:fragment slot="content"><p>Lorem ipsum dolor, sit amet consectetur adipisicing elit. Impedit dolorum optio, maiores rem facilis, beatae porro quasi itaque architecto qui eligendi provident dicta, fugit perferendis!</p></svelte:fragment>
		</AccordionItem>
		<AccordionItem>
			<svelte:fragment slot="lead"><Icon icon="material-symbols:add-task-rounded" width="31" height="31" /></svelte:fragment>
			<svelte:fragment slot="summary"><h2 class="text-2xl">Section 3 Preview</h2></svelte:fragment>
			<svelte:fragment slot="content"><p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Veniam consequuntur reprehenderit quod, error perspiciatis, ipsum nemo tempore, adipisci est quibusdam corporis assumenda ut facilis quisquam. Lorem ipsum dolor sit, amet consectetur adipisicing elit. Aliquid, sit?</p></svelte:fragment>
		</AccordionItem>
		<AccordionItem>
			<svelte:fragment slot="lead"><Icon icon="material-symbols:auto-transmission-sharp" width="31" height="31" /></svelte:fragment>
			<svelte:fragment slot="summary"><h2 class="text-2xl">Section 4 Preview</h2></svelte:fragment>
			<svelte:fragment slot="content"><p>Lorem, ipsum dolor sit amet consectetur adipisicing elit. Iure delectus animi in expedita, amet voluptate tempora nobis eum optio dicta culpa, quas beatae nesciunt blanditiis? Lorem ipsum dolor sit amet consectetur adipisicing elit. Earum sed et ipsum consectetur iusto aspernatur perferendis, omnis odio adipisci non dolore dicta placeat. Labore voluptates sed repudiandae blanditiis quae pariatur?</p></svelte:fragment>
		</AccordionItem>
		<!-- ... -->
	</Accordion>
	{#each sectionData as section}
    <Section {...section}/>
  {/each} 
	<!-- (sidebarRight) -->
	<!-- (pageHeader) -->
	<!-- Router Slot -->
	<slot />
	<!-- ---- / ---- -->
	<svelte:fragment slot="pageFooter">Page Footer</svelte:fragment>
	<!-- (footer) -->
</AppShell>