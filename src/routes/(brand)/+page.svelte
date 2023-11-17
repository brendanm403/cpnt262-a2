<script>
  import {homeData} from "$lib/section-data.js";
	import Section from "$lib/components/Section.svelte";
</script>

<!-- loops through data and creates the sections -->
{#each homeData as section}
<Section {...section}/>
{/each} 
