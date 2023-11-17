<script>
  import {aboutData} from "$lib/section-data.js"
  import Section from "$lib/components/Section.svelte";
</script>

<!-- loops through data and creates the sections -->
{#each aboutData as section}
<Section {...section} marginY="my-8"/>
{/each} 