<script>
  import Icon from "@iconify/svelte";
  export let icon;
  export let heading;
  export let para1 = "";
  export let para2 = "";
  export let para3 = "";
  export let marginY = "my-20"
</script>

<article class="{marginY} p-5 w-4/5 mx-auto">
  <div class="flex gap-2 items-center">
    <Icon {icon} width="31" height="31" />
    <h2 class="text-3xl text-tertiary-400-500-token">{heading}</h2>
  </div>
  <p class="my-5">{para1}</p>
  <p class="my-5">{para2}</p>
  <p class="my-5">{para3}</p>
</article>